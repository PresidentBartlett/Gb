# ProofSheet: Frontend Product Specification & UI Architectural Analysis
**Role:** Principal Product Designer & Lead Cloud Systems Architect  
**Project:** ProofSheet - Civic AI Assistant for Bangladesh  
**Target Demographic:** Low-to-medium digital literacy, spotty 4G connectivity, high-stress bureaucratic contexts.  

---

## 1. The Anxiety-Countering Visual Language: "Serene Minimalist Authority"

Typical Bangladeshi government portals (e.g., NIDw, e-Passport, NBR) induce cognitive load through stark contrast, dense unstructured text, bright primary colors (harsh reds/greens), and marquee scrolling text. ProofSheet’s design system must psychologically distance the user from this trauma through **Serene Minimalist Authority**.

### Color Palette Architecture
*   **Primary Base (Serene Authority):** `Deep Slate Green` (#1E3F36) – Evokes trust, official capacity, and calmness. Used for headers, primary typography, and the Hero Voice FAB.
*   **Secondary Accent (Clarity):** `Calming Teal` (#2A7A71) – Used for active states, interactive borders, and progression tracking.
*   **Background Foundation:** `Muted Off-White / Jute Sand` (#F4F2EE) – Reduces eye strain on low-end, high-glare Android viewports compared to stark white.
*   **Semantic Warnings (The "Reality" Color):** `Muted Terracotta` (#C05A46) – Replaces aggressive neon red. Used exclusively for highlighting unofficial extortion rates, warnings about missing documents, or dalal (broker) risks.

### Typography
*   **Dual-Script Harmony:** Utilize *Inter* for Latin/Banglish and *Noto Sans Bengali* (optimized for low-DPI rendering). 
*   **Hierarchy:** Large touch targets (min 44x44pt). High line-height (1.6) to accommodate complex Bengali vowel marks (kar/fala) which often clip in generic line-heights.

---

## 2. Zero-State Authority Dashboard

A blank chat interface causes "blank canvas paralysis" for users with low digital literacy. The zero-state must immediately project localized domain expertise.

**Wireframe & Component Concept:**
```text
[ Header: Logo ]  [ Toggle: EN / বাংলা / Banglish ]

[ Greeting ] "Ask me anything about your paperwork..."

[ The Ground-Truth Carousel (Auto-scrolling, High Contrast) ]
> "⚠️ Alert: Agargaon Passport Office currently facing 45-day delays for regular delivery."
> "💡 Tip: NID server maintenance usually occurs Tuesday at 2 AM. Avoid OTP requests then."

[ Expertise Panel Grid (Touch-Friendly Cards) ]
+-------------------------+ +-------------------------+
| 🪪 NID Correction      | | 🛂 e-Passport Renewal  |
| "Fix name/DOB errors"   | | "Step-by-step guidance" |
+-------------------------+ +-------------------------+
+-------------------------+ +-------------------------+
| 📄 e-TIN / Tax Return   | | 👶 Birth Registration   |
| "Calculate minimum tax" | | "City Corp vs Union"    |
+-------------------------+ +-------------------------+
```

---

## 3. The Voice-First Hero Input

Typing formal Bangla or Banglish on small screens is a massive friction point. The primary input method is voice.

### UI Architecture
*   **Visuals:** An oversized, central Floating Action Button (FAB) anchored just above a suppressed, secondary text-input field. 
*   **Micro-copy States:**
    *   *Default:* "Tap to speak in Bangla or Banglish..."
    *   *Active:* (Rippling Teal Animation) "Listening... speaks normally."
    *   *Processing:* (Pulsing Slate) "Understanding your voice..."
*   **Mobile Audio Browser API Logic (Low-End Android Optimized):**
    *   Use the `MediaRecorder` API requesting `audio/webm;codecs=opus` (highly compressed, perfect for spotty 4G).
    *   **Streaming Mechanics:** Instead of waiting for a 60-second recording to finish, implement **Chunked Audio Streaming**. Capture audio in 2000ms timeslices (`mediaRecorder.start(2000)`). Send base64-encoded chunks over WebSockets to the Modal backend.
    *   Modal runs a streaming Whisper STT pipeline, returning real-time transcription to the UI to build trust (the user sees their Banglish appearing live).

---

## 4. JSON-to-Action-Card Rendering Logic (Generative UI)

Standard LLM markdown output is unacceptable for this demographic. Walls of text will be ignored. The Modal backend will use Structured Outputs (e.g., Qwen 2.5 forced via JSON schema) to return semantic chunks. The Frontend intercepts this JSON and renders **React Components**.

**Mock JSON Payload from Modal:**
```json
{
  "greeting": "I can help you fix the spelling mistake in your father's name on your NID.",
  "financial_reality": { "official": "230 BDT", "street_rate": "1500 - 3000 BDT (Dalal)", "note": "You do NOT need a broker if you have your father's matriculation certificate." },
  "timeline": [
    { "step": 1, "title": "Gather Documents", "difficulty": "easy" },
    { "step": 2, "title": "Pay Sonali Bank Fee", "difficulty": "medium" }
  ]
}
```

**Component Mapping Strategy:**
1.  **P2P Opening Statement:** Rendered inside a soft, teal-bordered chat bubble. Warm, empathetic tone.
2.  **Financial Reality Check Card:** 
    *   A side-by-side UI block. 
    *   *Left (Green):* Official Government Fee (e.g., 230 BDT).
    *   *Right (Terracotta):* "Street Reality" (e.g., 1500 BDT).
    *   *Bottom Banner:* Actionable advice on how to avoid the extortion rate.
3.  **Procedural Timeline:** A vertical stepper component. "Easy" steps are green checks. "Hard/Friction" steps (like waiting in line at the Election Commission) are marked with yellow warning icons to manage expectations.

---

## 5. Open-Source Scaffolding Compatibility Matrix

We evaluated five frameworks against our strict technical requirements: (a) Layout Customization, (b) JSON/GenUI Interception, (c) Audio Input, and (d) AWS/Modal Bridge.

| Framework | (a) Layout Customization | (b) Custom UI / JSON Interception | (c) Audio Input Integration | (d) AWS/Modal Bridge (SSE/WS) | Verdict |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Vercel Chatbot** *(Next.js + AI SDK)* | **Excellent** – Full control over Tailwind and Shadcn layouts. | **Excellent** – Natively supports Generative UI (`streamUI` / `useObject`) to render React cards. | **Moderate** – No native raw mic support; requires custom `MediaRecorder` hook build. | **Excellent** – Next.js Route Handlers perfectly proxy SSE from Modal to the client. | **WINNER:** Highest flexibility for GenUI and layout. |
| **Chatbot-UI** | **Low** – Rigid, ChatGPT-clone layout. | **Poor** – Heavily tied to parsing Markdown streams. Hard to inject JSON Action Cards. | **Poor** – No native audio. | **Low** – Built strictly for OpenAI API shapes. Requires massive rewrites. | Reject. Too rigid for custom JSON. |
| **Chainlit** *(Python)* | **Low** – Layout is mostly fixed by the Python backend. | **Good** – Uses custom "Elements" to send UI blocks from Python to React. | **Excellent** – Recently added native streaming audio elements. | **Excellent** – Since it's Python, it runs *directly* on Modal and queries AWS natively. | **RUNNER UP:** Best for backend-heavy teams, but fails the strict Zero-State custom layout requirement. |
| **LibreChat** | **Low** – Very rigid enterprise clone. | **Poor** – Plugin system exists, but rendering bespoke UI cards is highly complex. | **Good** – STT/TTS built-in via plugins. | **Low** – Complex proxying required to hit custom Modal JSON endpoints. | Reject. Over-engineered for our needs. |
| **LobeChat** | **Moderate** – Highly customizable via CSS, but complex AntD architecture. | **Moderate** – Supports FC (Function Calling) plugins to render cards, but verbose. | **Excellent** – Native WebRTC and Audio API support. | **Moderate** – Can proxy via Edge, but plugin development for SSE is heavy. | Reject. Too bloated for spotty 4G viewports. |

### Architectural Recommendation
**Next.js + Vercel AI SDK 3.0.** 
*Why?* The Vercel AI SDK's `ai/rsc` (React Server Components) and `streamObject` paradigms are specifically designed to ingest streaming JSON from a custom backend (Modal) and yield frontend UI components (Action Cards) instantly. We will build a custom React hook for the Web Audio API.

---

## 6. Prototyping Engines Strategy (Bolt.new / Lovable.dev)

To rapidly validate this architecture, use AI scaffolding tools (Bolt.new or Lovable.dev) with strict, phased prompts to prevent them from hallucinating generic chat interfaces.

### Phase 1: Foundation & Zero-State Prompt
> "Bootstrap a Next.js 14 App Router project with Tailwind and Shadcn UI. Implement a color scheme with Primary: #1E3F36, Secondary: #2A7A71, Background: #F4F2EE. Build a 'Zero-State Authority Dashboard' component. It must include a top 'Ground-Truth' auto-scrolling ticker component, and a 2x2 Grid of touch-friendly cards for 'NID', 'Passport', 'Tax', 'Birth Certificate'. Do not build a standard chat input yet."

### Phase 2: The Voice Hero Input Prompt
> "Under the Zero-State dashboard, add a fixed bottom navigation area. The primary element must be an oversized, central Floating Action Button (FAB) with a microphone icon. Implement a custom React Hook using the `MediaRecorder` API. When pressed, the button should pulse using Tailwind animations. The hook should capture audio in 2-second chunks (`timeslice: 2000`) and console.log the base64 chunks. Below the FAB, place a minimal text input fallback."

### Phase 3: Generative UI & Vercel AI SDK Prompt
> "Integrate the Vercel AI SDK (`ai` package). Create a mock API route that streams a JSON object (using `experimental_streamObject` or similar) containing `{ greeting: string, financial_reality: { official: string, street_rate: string, advice: string }, steps: array }`. Build three React components: A Chat Bubble, a 'Financial Reality Card' splitting official vs street rates (use #C05A46 for street rate), and a Vertical Timeline Stepper. Wire the AI SDK `useChat` or `useObject` hook to render these components dynamically as the JSON streams in, replacing standard markdown text."

### AWS/Modal Dataflow Prototype Architecture
1. **Frontend (Browser):** Next.js captures 2s WebM audio chunks.
2. **Next.js API Route:** Proxies WebSockets to Modal.
3. **Modal (Serverless Python):** 
   - `whisper-v3-turbo` transcribes Audio to Text.
   - Embeds text, queries **AWS OpenSearch Serverless** for official BD Govt rules & localized ground-truths.
   - Passes context to `Llama-3.1-8B-Instruct`.
   - Forces structured JSON output matching frontend schema.
4. **Next.js UI:** Receives JSON stream -> Renders Semantic React Action Cards.