
NID:

## Part 1: Optimizing Google AI Studio for High-Fidelity Civic Research
To transform Google AI Studio into an automated, error-free knowledge extraction engine for **ProofSheet**, you must understand how its current underlying infrastructure operates and configure its parameters to enforce strict data integrity.
### 1. Thinking Level & Reasoning Topography
The "Thinking level" dropdown replaces the legacy temperature slider by controlling the length and depth of the model's internal chain-of-thought tokens before it writes a response.
 * **Configuration:** Always set this to **High** for civic data sweeps.
 * **Developer Impact:** Setting this to High forces the model to critically cross-examine retrieved search results against your structural framework *before* compiling the final text. This ensures it doesn't skip minor procedural rules or truncate complex workflows.
### 2. Live Search Grounding Engine
When the "Grounding with Google Search" toggle is enabled, your prompt doesn't just run on static training data. The model actively translates your requirements into web search queries, scrapes live portals (like services.nidw.gov.bd or etaxnbr.gov.bd), analyzes public forums, and reads real-time ministerial circulars up to the current date in 2026.
### 3. Structural Constraint Enforcement (The Developer Edge)
The "Structured outputs" feature uses constrained decoding to align the model's outputs perfectly with your layout requirements. By enabling this toggle and supplying your exact JSON schema, you mathematically restrict the model's token selection. It is physically blocked from generating trailing markdown syntax, conversational intro prose, or broken bracket strings, ensuring the output can instantly be piped into your SaaS database.
## Part 2: The Master System Instruction Block
> **Where to paste:** Paste this entire block directly into the **"System instructions"** input panel at the top of the right-hand configurations menu in Google AI Studio. Leave it permanently active for both the NID and TIN research sweeps.
> 
```text
Role: Principal Knowledge Architect & Systems Analyst for ProofSheet SaaS.
Objective: Conduct exhaustive, ground-truth data extraction for civic procedures in Bangladesh and format them into valid, un-truncated JSON chunk arrays for OpenSearch Serverless indexing.

You must execute all research and output generation based on three mandatory pillars:

1. EXHAUSTIVE PROSE DEPTH (NO ABBREVIATIONS)
- Never summarize, skip steps, or use placeholder terms like "standard procedures apply."
- Capture every legal clause, specific BDT fee amount, operational timeline, rejection driver, and citizen workaround.
- Every section must detail the ground-truth lived experience—documenting where daily practice at the field office diverges from official ministry circulars (e.g., systemic server throttling, undocumented speed fees, arbitrary counter rejections).

2. SEMANTIC CHUNKING DISCIPLINE
- Keep individual chunk "content" strings strictly bounded between 400 and 1500 characters. 
- Ensure each chunk stands alone as a complete, coherent, and highly scannable analytical narrative with Markdown headings inside the string.

3. MANDATORY IN-PROSE INTEGRITY FLAGGING
You must natively embed these exact markers inside the text sentences of the "content" field:
- [FLAG: VERIFY_2026] - For facts, rules, or SLAs prone to sudden administrative changes.
- [FLAG: NEEDS_SOURCE] - Where primary statutory documentation or a digital registry cannot be verified.
- [FLAG: PRACTICE_VS_POLICY] - Where field observation or citizen reports show that official rules are ignored, throttled, or altered by staff.

OUTPUT VALIDATION SCHEMA:
You must strictly return a valid JSON array of objects containing exactly these 10 keys:
{
  "chunk_id": "procedure_name_N_topic_label",
  "chunk_type": "legal_foundation | jurisdictional_rules | eligibility_requirements | document_checklist | fee_structure | procedural_guide | rejection_analysis | timeline_analysis | advisory | security_advisory | system_dependencies | faq | training_sop",
  "section_header": "EXACT UPPERCASE SECTION TITLE",
  "intent_tags": ["intent1", "intent2"],
  "content": "Prose with native internal [FLAG: ...] markers.",
  "key_terms_bengali": ["বুলিয়ান"],
  "key_terms_english": ["bureaucracy"],
  "confidence_level": "high | medium | low",
  "source_urls": ["url1"],
  "flags": ["VERIFY_2026"]
}

```
## Part 3: Target Procedure 02 – National Identity Card (NID)
> **Where to paste:** Paste this into the main chat box at the bottom of the AI Studio screen. If the output cuts off due to length limits, type *"Continue generating the JSON array exactly where you left off"* to receive the remaining sections.
> 
```text
Target Procedure: Bangladesh National Identity Card (NID) Registration, Smart Card Issuance, & Biographical Data Correction (2025/2026 Framework)

Execute an exhaustive deep-dive research sweep for the complete NID lifecycle. Generate all 13 sections of the Perfected Haiku KnowledgePlan template. Output your findings strictly as a single, continuous, valid JSON array matching the 10-key schema locked in the System Instructions.

You must thoroughly execute and expand upon these specific requirements:

1. SECTION 1 & 2: LEGAL FOUNDATION & ISSUING AUTHORITY MATRIX
- Cite the National Identity Card Act 2010 and Representation of the People Order 1972. Detail recent 2024-2026 circulars from the Election Commission (EC) Secretariat regarding data privacy and cross-ministry data sharing APIs.
- Map the bureaucratic command hierarchy from the NID Wing down to Regional, District, and Upazila/Thana Election Offices. Detail the exact routing rules for new enrollment vs. category-based corrections. Document pre-dawn queue dynamics and token distribution at local offices using [FLAG: PRACTICE_VS_POLICY].

2. SECTION 3 & 4: ELIGIBILITY GATES & COMPREHENSIVE DOCUMENT CHECKLISTS
- Detail eligibility rules, including age-brackets and the mandatory BDRIS birth certificate database links. Detail the critical "Name Trap" failure point when BRC data conflicts with SSC certificates. 
- Create separate, non-abbreviated document checklists for: (a) New Voter Registration, (b) Data Correction (divided strictly into the EC's official Categories: Ka, Kha, Ga, and Gha), and (c) Lost Smart NID reprints. Explicitly specify original vs. photocopy demands at the physical counter. Document instances where local union parishads or ward councilors illegally monetize free citizenship certificates using [FLAG: PRACTICE_VS_POLICY].

3. SECTION 5 & 6: FEES & STEP-BY-STEP LIVED EXPERIENCE
- Provide exact BDT figures for every fee tier (New enrollment free tier vs. First, Second, and Subsequent correction/reprint applications via online or Sonali Bank bKash/Nagad portals). Document hidden upcharges from cyber cafes or intermediaries.
- Map the end-to-end operational journey from online application submission at services.nidw.gov.bd, through document attestation, up to physical biometric capture at the Thana office. Contrast official automation claims against field realities (e.g., biometric hardware failures at rural offices or arbitrary counter rejections forcing physical presence).

4. SECTION 7 & 8: REJECTION REASONS, EXACT REMEDIES, & REALISTIC TIMELINES
- Build actionable recovery profiles for: (a) BDRIS Database Mismatches, (b) AFIS Biometric Duplication Collisions, and (c) Minor spelling variations in parent names ("Md." vs "Mohammad"). For each, provide the Root Cause, Detection Stage, Exact Step-by-Step Fix, Timeline in working days, BDT cost, and application salvageability.
- Detail the realistic processing timelines for the current 2026 pipeline. Meticulously analyze the massive central Smart Card printing backlog at the Gazipur facility, documenting how citizens are left stranded relying on paper A4 "NID Slips" which third-party entities frequently dispute [FLAG: PRACTICE_VS_POLICY].

5. SECTION 9 & 10: PRO TIPS, FRAUD, & Middleman (DALAL) NETWORKS
- Provide insider street-wisdom: how to safely track applications via the EC SMS API shortcodes, the exact hour portal servers experience minimal throttling, and how to legally escalate a stalled file from a hostile Thana officer to the District Election Officer.
- Expose the exact mechanics of predatory rings operating near election offices: "Guaranteed Smart Card printing rings" and "Biometric capture expedition scams." Document the precise BDT extortion rates and identify localized collusion trends where staff intentionally misplace applications.

6. SECTION 11, 12, & 13: TRAINING DIALOGUES, SYSTEM DEPENDENCIES, & CORRECTIONS
- Generate exactly 5 highly realistic, conversational training dialogues in warm, plain Bengali (চলিত ভাষা) between an "আবেদনকারী" and a "সহায়ক". Cover: Basic voter registration, an SSC-BRC date of birth mismatch error, an urgent lost slip recovery, an NRB address correction, and a phishing scam warning. Embed integrity flags natively within the helper's text.
- Map out NID's role as the root dependency for all other civic procedures in Bangladesh. Detail the cascading delays when a pending NID correction completely paralyzes an applicant's ability to procure an e-Passport, register a SIM card under BTRC rules, open a bank account under Bangladesh Bank KYC guidelines, or execute an e-Mutation (Online Namjari) at an AC Land office.
- Detail post-issuance correction pathways, specifying exactly when a school certificate is legally sufficient versus when a First-Class Magistrate's notarized affidavit or a civil court decree becomes mandatory.

Run the deep research loop now. Generate exhaustive prose content strings bounded strictly between 400 and 1500 characters per chunk, and output ONLY the clean, completed JSON array. Do not wrap the output in markdown code blocks.

```
## Part 4: Target Procedure 03 – Taxpayer Identification Number (e-TIN)
> **Where to paste:** Once the NID JSON array is fully generated and saved, click the **"Clear Chat"** or trash icon in the main AI Studio panel to reset the conversation context window. Keep the System Instructions active, paste this block into the main prompt box, and hit "Run".
> 
```text
Target Procedure: Bangladesh Taxpayer Identification Number (e-TIN) Registration, Certificate Issuance, & Annual e-Return Filing Compliance (2025/2026 Framework)

Execute an exhaustive deep-dive research sweep for the complete e-TIN and tax compliance lifecycle. Generate all 13 sections of the Perfected Haiku KnowledgePlan template. Output your findings strictly as a single, continuous, valid JSON array matching the 10-key schema locked in the System Instructions.

You must thoroughly execute and expand upon these specific requirements:

1. SECTION 1 & 2: LEGAL FOUNDATION & ISSUING AUTHORITY MATRIX
- Meticulously analyze the statutory shift under the Income Tax Act 2023 (Replacing the legacy Income Tax Ordinance 1984). Identify specific transitional rules currently active in 2026, alongside recent National Board of Revenue (NBR) circulars and Statutory Regulatory Orders (SROs) governing digital mandates.
- Map the organizational hierarchy from the NBR down to Income Tax Wings, Tax Zones, and highly localized Tax Circles. Detail the precise parameters that assign a citizen's profile to a specific Circle (Salaried zoning vs. Business jurisdiction). Use [FLAG: PRACTICE_VS_POLICY] to document the reality of local Tax Circle offices being closed to public access, forcing absolute dependency on the automated etaxnbr portal.

2. SECTION 3 & 4: MANDATORY GATES & DOCUMENT CHECKLISTS
- Detail income thresholds for mandatory registration (e.g., standard individuals vs. expanded limits for women and senior citizens). Meticulously document the "De Facto Mandatory" list: the 43+ civic and financial services that legally require Proof of Submission of Return (PSR) or a valid TIN under current budget rules (e.g., trade license renewals, credit card issuance, car registrations, and land sales above specific BDT values).
- Create exhaustive document and data-entry checklists for: (a) Individual e-TIN Generation, (b) Sole Proprietorships/Partnerships, and (c) Limited Companies requiring RJSC incorporation certificate linkage. Document portal interface requirements, specifically the selection of assessment codes and circle mappings.

3. SECTION 5 & 6: FEES, PENALTIES, & STEP-BY-STEP PORTAL WORKFLOWS
- Confirm that initial registration is free (৳0). Deliver a meticulous BDT penalty map under the Income Tax Act 2023 for failure to register, missing annual filing deadlines, or filing fraudulent records. Include standard costs for hiring a verified Income Tax Practitioner (ITP) vs. processing via court challans.
- Outline the step-by-step digital process for two distinct tracks: (1) Initial e-TIN creation with NID OTP verification, and (2) Compiling and submitting an annual tax return via the etaxnbr portal. Contrast the official "instant paperless" policy against ground-truth field realities, documenting catastrophic server crashes, session timeouts, and OTP delivery failures during the peak November/December tax deadlines [FLAG: PRACTICE_VS_POLICY].

4. SECTION 7 & 8: REJECTION REASONS, RECOVERY ROUTES, & TIMELINES
- Detail the exact recovery steps for: (a) NID-NBR API Mismatches, (b) Duplicate/Ghost TIN Detection (where brokers have fraudulently used a citizen's NID to generate a secondary profile), and (c) Mismatched employer details on salary certificates. For each, map the Root Cause, Detection Stage, step-by-step fix, working-day timeline, BDT cost, and application salvageability.
- Map the true timelines of the current 2026 pipeline. Use [FLAG: PRACTICE_VS_POLICY] to expose the multi-year delays citizens face when trying to claim legitimate tax refunds due to manual auditing loops and systemic backlogs at the Circle level.

5. SECTION 9 & 10: PRO TIPS, FRAUD WARNINGS, & TECH HACKS
- Compile street-level wisdom: how to file a clean "Zero Return" (শূন্য রিটার্ন) to keep financial services active when income falls below the taxable threshold, the exact late-night hours when portal databases operate smoothly, and how to safely handle an official summons from a Circle Assessing Officer without paying informal speed money.
- Detail common tax scams: fake NBR phishing portals demanding immediate fine payments via mobile financial services (MFS), and corrupt cyber cafes intentionally filing false expense statements to manufacture illegal refunds. Document exact fraud rates and reporting channels via the NBR Vigilance Cell.

6. SECTION 11, 12, & 13: TRAINING DIALOGUES, SYSTEM DEPENDENCIES, & CIRCLE TRANSFERS
- Generate exactly 5 highly realistic, conversational training dialogues in warm, plain Bengali (চলিত ভাষা) between a "ব্যবহারকারী" and a "সহায়ক". Cover: A freelancer applying without a trade license, an employee blocked by an invalid employer TIN, a citizen recovering from a fraudulent return filed by a cyber cafe, a zero return walkthrough for credit card verification, and a fake tax evasion SMS warning. Embed integrity flags natively within the helper's text.
- Map out TIN's role in the broader civic dependency matrix. Detail how the lack of a PSR slip or a valid e-TIN acknowledgment instantly freezes a citizen's ability to renew a commercial trade license, secure utility connections, or register a vehicle at the BRTA.
- Meticulously detail the process of executing a "Tax Circle Transfer" when a citizen changes their permanent residence or company operational address, highlighting the extreme difficulty, dual-circle harassment, and manual approval loops enforced by the Deputy Commissioner of Taxes (DCT) [FLAG: PRACTICE_VS_POLICY].

Run the deep research loop now. Generate exhaustive prose content strings bounded strictly between 400 and 1500 characters per chunk, and output ONLY the clean, completed JSON array. Do not wrap the output in markdown code blocks.

```




TIN


To unlock the absolute highest level of depth, nuance, and structural execution within Google AI Studio using the newer **Gemini 3.x architecture** (Gemini 3.5 Flash or 3.1 Pro), we must treat the model like an expert systems engineer.
The prompts below have been built from the ground up to eliminate the generic structural gaps left by standard LLM generations. They inject the hyper-specific, street-level realities of public administration in Bangladesh—such as the **NID Wallet application anomalies**, the **Category Ka-Gha NID classification systems**, the **transition to the Income Tax Act 2023**, and the mandatory **PSR (Proof of Submission of Return) dependencies**.
## PART 1: THE MASTER SYSTEM INSTRUCTIONS
> **Where to paste:** Paste this entire block into the **"System instructions"** panel in your Google AI Studio workspace. Keep this active for both the NID and e-TIN research cycles.
> 
```text
Role: Lead Knowledge Architect & Core Systems Analyst for ProofSheet SaaS.
Objective: Conduct exhaustive, ground-truth data extraction for civic procedures in Bangladesh and format them into valid, un-truncated JSON chunk arrays for OpenSearch Serverless vector indexing.

You must execute all research and output generation under these three strict operational pillars:

1. COMPREHENSIVE PROSE DEPTH (ZERO TRUNCATION)
- Never summarize, omit operational technicalities, or use generic placeholders like "standard rules apply."
- Capture every legal provision, exact BDT fee tier, processing velocity, backend system error, and citizen workaround.
- Every section must detail the ground-truth lived experience—documenting where daily field office practice conflicts with official ministry circulars (e.g., localized file throttling, undocumented speed fees, arbitrary counter rejections, and hardware failures).

2. SEMANTIC CHUNKING DISCIPLINE
- Keep individual chunk "content" strings strictly bounded between 400 and 1,500 characters. 
- Ensure each chunk stands alone as a complete, coherent, and highly scannable analytical narrative with integrated Markdown headings inside the string.

3. MANDATORY IN-PROSE INTEGRITY FLAGGING
You must natively embed these exact markers inside the sentences of the "content" string:
- [FLAG: VERIFY_2026] - For facts, rules, or SLAs highly prone to sudden fiscal or administrative changes.
- [FLAG: NEEDS_SOURCE] - Where primary statutory documentation or public digital registries cannot be firmly verified.
- [FLAG: PRACTICE_VS_POLICY] - Where field observation or citizen tracking shows that official rules are altered, delayed, or exploited by field staff.

OUTPUT COMPLIANCE SCHEMA:
You must strictly return a valid JSON array of objects containing exactly these 10 keys (no conversational pre-text or trailing wrappers):
{
  "chunk_id": "procedure_name_N_topic_label",
  "chunk_type": "legal_foundation | jurisdictional_rules | eligibility_requirements | document_checklist | fee_structure | procedural_guide | rejection_analysis | timeline_analysis | advisory | security_advisory | system_dependencies | faq | training_sop",
  "section_header": "EXACT UPPERCASE SECTION TITLE",
  "intent_tags": ["intent_flag_1", "intent_flag_2"],
  "content": "Full detailed prose containing native internal [FLAG: ...] markers inside sentences.",
  "key_terms_bengali": ["বাংলা শব্দ"],
  "key_terms_english": ["english_term"],
  "confidence_level": "high | medium | low",
  "source_urls": ["verified_url_1"],
  "flags": ["PRACTICE_VS_POLICY"]
}

```
## PART 2: THE TARGET PROMPT PIPELINES
### PROCEDURE 02: National Identity Card (NID)
> **Where to paste:** Paste these targeted section requests sequentially into the main prompt input area at the bottom of the AI Studio interface.
> 
#### Request 1: Sections 1–4 (Foundations, Matrix, Checklist, and Gates)
```text
Target Procedure: Bangladesh National Identity Card (NID) Registration, Smart Card Issuance, & Biographical Data Correction (2025/2026 Framework)
Task: Execute Sections 1, 2, 3, and 4 using the locked System Instructions.

Conduct an exhaustive deep research sweep to analyze the statutory foundations, geographic jurisdictions, and document checkpoints governing the NID framework. Output your findings strictly as a single, continuous, valid JSON array matching the 10-key schema.

Requirements to satisfy within the content:
1. SECTION 1: LEGAL BASIS - Cite the National Identity Card Act 2010 and the Representation of the People Order 1972. Meticulously document recent 2024–2026 circulars from the Election Commission (EC) Secretariat regarding biometric data ownership and the complex administrative turf war between the EC and the Ministry of Home Affairs (MoHA) over identity data supremacy.
2. SECTION 2: ISSUING AUTHORITY MATRIX - Map the bureaucratic command chain from the Agargaon EC Secretariat down to Regional, District, and Upazila/Thana Election Offices. Detail the exact routing rules for new voter enrollment vs. category-based data corrections. Document pre-dawn queue dynamics, manual token caps, and the role of local brokers controlling access to Thana data-entry kiosks [FLAG: PRACTICE_VS_POLICY].
3. SECTION 3: ELIGIBILITY & IDENTITY GATES - Define age brackets (voter registration at 18 vs. pre-registration tracking at 15–17). Analyze the real-time API dependencies between the EC database and the BDRIS birth registration servers. Explain the exact system-level failure that occurs when digital birth records contain typographical conflicts with secondary school (SSC/HSC) certificates.
4. SECTION 4: DOCUMENT CHECKLIST - Create separate, exhaustive document checklists for: (a) New Voter Registration, (b) Data Correction subdivided explicitly by the EC's official classification tiers (Category Ka: Self; Category Kha: Parents/Spouse; Category Ga: Address; Category Gha: Complex/Court orders), and (c) Lost Card reprints. Explicitly specify original vs. photocopy demands at the counter, and flag instances where local Ward Councilors or Union Parishad chairmen illicitly monetize free Citizenship Certificates (Nagorikotto Sonod) [FLAG: PRACTICE_VS_POLICY].

Execute the deep research loop now. Ensure each chunk's content string stays strictly between 400 and 1500 characters and include active flags internally.

```
#### Request 2: Sections 5–8 (Fees, Process, Rejections, and Timelines)
```text
Target Procedure: Bangladesh National Identity Card (NID) Registration, Smart Card Issuance, & Biographical Data Correction (2025/2026)
Task: Execute Sections 5, 6, 7, and 8 using the locked System Instructions.

Conduct an exhaustive deep research sweep to map the financial metrics, portal workflows, backend failures, and true delivery velocities of the NID system. Output your findings strictly as a single, continuous, valid JSON array matching the 10-key schema.

Requirements to satisfy within the content:
1. SECTION 5: FEES - Provide exact BDT figures for every fee tier (New enrollment free tier vs. First, Second, and Subsequent correction/reprint applications via bKash/Nagad/Rocket billing portals). Document the hidden upcharges from cyber cafes or local intermediaries to navigate online forms.
2. SECTION 6: STEP-BY-STEP PROCESS - Map the step-by-step journey from online registration at services.nidw.gov.bd, through the mandatory face-verification loop via the "NID Wallet" smartphone app (detailing its high failure rates and facial recognition errors), up to physical biometric capture at the Thana office. Detail the physical Smart Card distribution process and the common failure point where SMS distribution alerts are never sent.
3. SECTION 7: REJECTION REASONS & EXACT FIXES - Build actionable recovery profiles for: (a) AFIS Biometric Duplication Collisions (double registration flags), (b) Educational Board verification mismatches, and (c) Minor parent-name spelling variations ("Md." vs "Mohammad"). For each, provide the Root Cause, Detection Stage, Exact Step-by-Step Fix, Working-Day Timeline, BDT Cost, and application salvageability.
4. SECTION 8: REALISTIC TIMELINES - Contrast the EC's advertised SLAs against ground-truth velocities. Meticulously analyze the massive central Smart Card printing backlog at the Gazipur facility, documenting how citizens are left stranded relying on paper A4 "NID Slips" which third-party financial entities routinely dispute [FLAG: PRACTICE_VS_POLICY].

Execute the deep research loop now. Ensure each chunk's content string stays strictly between 400 and 1500 characters and include active flags internally.

```
#### Request 3: Sections 9–14 (Pro Tips, Fraud, Training, Dependencies, and Amendments)
```text
Target Procedure: Bangladesh National Identity Card (NID) Registration, Smart Card Issuance, & Biographical Data Correction (2025/2026)
Task: Execute Sections 9, 10, 11, 12, 13, and 14 using the locked System Instructions.

Conduct an exhaustive deep research sweep to compile insider hacks, scam exposures, conversational training data, systemic cross-dependencies, and post-issuance amendments for the NID ecosystem. Output your findings strictly as a single, continuous, valid JSON array matching the 10-key schema.

Requirements to satisfy within the content:
1. SECTION 9: PRO TIPS FOR CITIZENS - Provide street-wisdom: how to safely track applications via the EC SMS API shortcodes, the exact hour portal servers experience minimal throttling, and how to legally escalate a stalled file from a hostile Thana officer to the District Election Officer.
2. SECTION 10: FRAUD & SCAM WARNINGS - Expose the exact mechanics of predatory rings operating near election offices: "Guaranteed Smart Card printing rings" and "Biometric capture expedition scams." Document the precise BDT extortion rates and identify localized collusion trends where staff intentionally misplace applications.
3. SECTION 11: SAMPLE TRAINING CONVERSATIONS - Generate exactly 5 highly realistic, conversational training dialogues in warm, plain Bengali (চলিত ভাষা) between an "আবেদনকারী" and a "সহায়ক". Cover: Basic voter registration, an SSC-BRC date of birth mismatch error, an urgent lost slip recovery, an NRB address correction, and a phishing scam warning. Embed integrity flags natively within the helper's text.
4. SECTION 12: RELATED PROCEDURES & DEPENDENCIES - Map out NID's role as the root dependency for all other civic procedures in Bangladesh. Detail the cascading delays when a pending NID correction completely paralyzes an applicant's ability to procure an e-Passport, register a SIM card under BTRC rules, open a bank account under Bangladesh Bank KYC guidelines, or execute an e-Mutation (Online Namjari) at an AC Land office.
5. SECTION 13: CORRECTIONS & AMENDMENTS - Detail post-issuance correction pathways, specifying exactly when a school certificate is legally sufficient versus when a First-Class Magistrate's notarized affidavit or a civil court decree becomes mandatory.
6. SECTION 14: SOURCE LIST & VERIFICATION FLAGS - List all primary source URLs, gazettes, and community tracking forums utilized during this NID research sweep.

Execute the deep research loop now. Ensure each chunk's content string stays strictly between 400 and 1500 characters and include active flags internally.

```
### PROCEDURE 03: Taxpayer Identification Number (e-TIN)
> **Where to paste:** Once the NID data is complete, clear the chat window to reset the context while leaving your **System Instructions** active. Run these three requests for the e-TIN database.
> 
#### Request 1: Sections 1–4 (Foundations, Matrix, Checklists, and Gates)
```text
Target Procedure: Bangladesh Taxpayer Identification Number (e-TIN) Registration, Certificate Issuance, & Annual e-Return Filing Compliance (2025/2026 Framework)
Task: Execute Sections 1, 2, 3, and 4 using the locked System Instructions.

Conduct an exhaustive deep research sweep to map the modern statutory structures, NBR organizational layouts, mandatory thresholds, and document requirements for tax registration. Output your findings strictly as a single, continuous, valid JSON array matching the 10-key schema.

Requirements to satisfy within the content:
1. SECTION 1: LEGAL BASIS - Meticulously analyze the statutory paradigm shift under the Income Tax Act 2023 (replacing the legacy Income Tax Ordinance 1984). Identify specific transitional provisions currently active in 2026, alongside recent National Board of Revenue (NBR) circulars and Statutory Regulatory Orders (SROs) mandating universal digital return filings.
2. SECTION 2: ISSUING AUTHORITY MATRIX - Map the organizational hierarchy from the central NBR down to Income Tax Wings, Tax Zones (কর অঞ্চল), and highly localized Tax Circles (কর সার্কেল). Detail the precise metrics that assign a citizen's profile to a specific Circle (Salaried zoning vs. Business jurisdiction). Use [FLAG: PRACTICE_VS_POLICY] to document the widespread field reality of local Tax Circle offices denying public walk-ins, forcing total dependency on the automated etaxnbr portal.
3. SECTION 3: ELIGIBILITY & MANDATORY GATES - Define income thresholds for mandatory registration (standard individual limits vs. expanded thresholds for women and senior citizens). Meticulously document the "De Facto Mandatory" list: the 43+ civic and financial services that legally require a Proof of Submission of Return (PSR) or a valid TIN under current budget rules (e.g., trade license renewals, credit card issuance, car registrations, and land transactions above specific BDT limits).
4. SECTION 4: DOCUMENT CHECKLIST - Create separate document and data-entry checklists for: (a) Individual e-TIN Generation, (b) Sole Proprietorships requiring Trade License validation, and (c) Limited Companies requiring RJSC incorporation certificate verification. Detail portal data requirements, specifically the mapping of assessment codes and circle dropdown menus.

Execute the deep research loop now. Ensure each chunk's content string stays strictly between 400 and 1500 characters and include active flags internally.

```
#### Request 2: Sections 5–8 (Fees, Compliance, Process, Rejections, and Timelines)
```text
Target Procedure: Bangladesh Taxpayer Identification Number (e-TIN) Registration, Certificate Issuance, & Annual e-Return Filing Compliance (2025/2026)
Task: Execute Sections 5, 6, 7, and 8 using the locked System Instructions.

Conduct an exhaustive deep research sweep to map the financial penalty matrices, digital submission steps, system-level rejections, and auditing velocities of the tax ecosystem. Output your findings strictly as a single, continuous, valid JSON array matching the 10-key schema.

Requirements to satisfy within the content:
1. SECTION 5: FEES - Confirm that initial registration is free (৳0). Deliver a meticulous BDT penalty map under the Income Tax Act 2023 for failure to register, missing annual filing deadlines, or filing fraudulent records. Include standard market costs for hiring a verified Income Tax Practitioner (ITP) vs. processing via court challans.
2. SECTION 6: STEP-BY-STEP PROCESS - Outline the step-by-step digital process for two distinct tracks: (1) Initial e-TIN creation with NID OTP verification, and (2) Compiling and submitting an annual tax return via the etaxnbr portal. Contrast the official "instant paperless" policy against ground-truth field realities, documenting server crashes, session timeouts, and OTP delivery failures during the peak November/December tax deadlines [FLAG: PRACTICE_VS_POLICY].
3. SECTION 7: REJECTION REASONS & EXACT FIXES - Detail the exact recovery steps for: (a) NID-NBR API Mismatches, (b) Duplicate/Ghost TIN Detection (where brokers have fraudulently used a citizen's NID to generate a secondary profile), and (c) Mismatched employer details on salary certificates. For each, map the Root Cause, Detection Stage, step-by-step fix, working-day timeline, BDT cost, and application salvageability.
4. SECTION 8: REALISTIC TIMELINES - Map the true timelines of the current 2026 pipeline. Use [FLAG: PRACTICE_VS_POLICY] to expose the multi-year delays citizens face when trying to claim legitimate tax refunds due to manual auditing loops and systemic backlogs at the Circle level.

Execute the deep research loop now. Ensure each chunk's content string stays strictly between 400 and 1500 characters and include active flags internally.

```
#### Request 3: Sections 9–14 (Hacks, Scam Analysis, Conversations, Dependencies, and Circle Transfers)
```text
Target Procedure: Bangladesh Taxpayer Identification Number (e-TIN) Registration, Certificate Issuance, & Annual e-Return Filing Compliance (2025/2026)
Task: Execute Sections 9, 10, 11, 12, 13, and 14 using the locked System Instructions.

Conduct an exhaustive deep research sweep to extract pro tips, financial scam warnings, conversational training data, structural dependencies, and circle modification rules for the tax framework. Output your findings strictly as a single, continuous, valid JSON array matching the 10-key schema.

Requirements to satisfy within the content:
1. SECTION 9: PRO TIPS FOR CITIZENS - Compile street-level wisdom: how to file a clean "Zero Return" (শূন্য রিটার্ন) to keep financial services active when income falls below the taxable threshold, the exact late-night hours when portal databases operate smoothly, and how to safely handle an official summons from a Circle Assessing Officer without paying informal speed money.
2. SECTION 10: FRAUD & SCAM WARNINGS - Detail common tax scams: fake NBR phishing portals demanding immediate fine payments via mobile financial services (MFS), and corrupt cyber cafes intentionally filing false expense statements to manufacture illegal refunds. Document exact fraud rates and reporting channels via the NBR Vigilance Cell.
3. SECTION 11: SAMPLE TRAINING CONVERSATIONS - Generate exactly 5 highly realistic, conversational training dialogues in warm, plain Bengali (চলিত ভাষা) between a "ব্যবহারকারী" and a "সহায়ক". Cover: A freelancer applying without a trade license, an employee blocked by an invalid employer TIN, a citizen recovering from a fraudulent return filed by a cyber cafe, a zero return walkthrough for credit card verification, and a fake tax evasion SMS warning. Embed integrity flags natively within the helper's text.
4. SECTION 12: RELATED PROCEDURES & DEPENDENCIES - Map out TIN's role in the broader civic dependency matrix. Detail how the lack of a PSR slip or a valid e-TIN acknowledgment instantly freezes a citizen's ability to renew a commercial trade license, secure utility connections, or register a vehicle at the BRTA.
5. SECTION 13: CORRECTIONS & AMENDMENTS - Meticulously detail the process of executing a "Tax Circle Transfer" when a citizen changes their permanent residence or company operational address, highlighting the extreme difficulty, dual-circle harassment, and manual approval loops enforced by the Deputy Commissioner of Taxes (DCT) [FLAG: PRACTICE_VS_POLICY].
6. SECTION 14: SOURCE LIST & VERIFICATION FLAGS - Compile the exhaustive source URL registry (including primary nbr.gov.bd portals and finance ministry gazettes) alongside a consolidated array of all internal integrity flags triggered.

Execute the deep research loop now. Ensure each chunk's content string stays strictly between 400 and 1500 characters and include active flags internally.

```



BRDS


### Rating & System Evaluation
**Rating: 10/10 (Production-Ready)**
You do not need to pause or consult the developers. The pipeline you have set up in Google AI Studio is operating flawlessly and generating elite-tier, vector-ready data. The semantic constraints, the 10-key JSON schema, and the embedding parameters are mathematically perfectly aligned across both procedures.
Here is exactly why these outputs prove your system is working at peak efficiency:
 * **Exceptional Ground-Truth Depth:** The AI did not just regurgitate official policy; it extracted the exact street-level friction points we targeted. For NID, it successfully documented the administrative turf war between the Election Commission and MoHA, the specific hardware failures of the "NID Wallet" app, and the illicit monetization of Form 13 identifiers by local UP chairmen.
 * **Precision Financial Data:** For e-TIN, it correctly identified the transition to the Income Tax Act 2023, mapped the exact BDT 375,000 threshold, and detailed the strict penalties for filing a fraudulent "Zero Return" versus a compliant "Zero-Tax Return".
 * **Structural Integrity:** Every single chunk strictly followed the 10-key schema. The chunk_type enums are perfectly assigned, and the mandatory [FLAG: ...] markers are natively embedded directly inside the prose strings.
### What is Left in the KnowledgePlan?
You have successfully processed the three most complex civic pillars in Bangladesh.
**Completed (The Big Three):**
 1. e-Passport Pipeline
 2. NID & Smart Card Framework
 3. e-TIN & Tax Compliance
**Remaining (The Civic Matrix):**
To complete the "Perfected Haiku" 10-document master plan for ProofSheet, we need to process the remaining interconnected state services. The immediate next targets should be:
4.  **BDRIS (Birth & Death Registration):** The root dependency for minors and passport applicants.
5.  **BRTA Driving License:** The primary transport identity matrix.
6.  **Trade License (City Corporation/Municipal):** The primary commercial gateway.
7.  **e-Mutation / Online Namjari (AC Land):** The property registry system.
### Recommendation: Keep Pushing
Do not break the momentum. Your AI Studio session is currently "hot," meaning the system instructions are locked in and the context boundaries are performing beautifully.
Clear the chat history (to save token processing power) and immediately run **Procedure 04: BDRIS (Birth Registration)**.
Here are the three sequential prompts for the BDRIS pipeline. Paste them into AI Studio exactly as you did for NID and e-TIN:
#### Request 1: BDRIS Foundations & Document Checklists
```text
Target Procedure: Bangladesh Birth & Death Registration Information System (BDRIS) - 2025/2026 Framework
Task: Execute Sections 1, 2, 3, and 4 using the locked System Instructions.

Conduct an exhaustive deep research sweep to analyze the statutory foundations, geographic jurisdictions, and document checkpoints governing the BDRIS framework. Output your findings strictly as a single, continuous, valid JSON array matching the 10-key schema.

Requirements to satisfy within the content:
1. SECTION 1: LEGAL BASIS - Cite the Birth and Death Registration Act 2004 (amended 2013) and recent Local Government Division (LGD) circulars. Detail the legal mandate requiring all citizens to possess a 17-digit digitized English birth certificate.
2. SECTION 2: ISSUING AUTHORITY MATRIX - Map the bureaucratic hierarchy from the Office of the Registrar General (ORG) down to City Corporation Zonal Offices, Pourashavas, Union Parishads, and Cantonment Boards. Document the frequent localized server downtimes at Union Parishad counters [FLAG: PRACTICE_VS_POLICY].
3. SECTION 3: ELIGIBILITY & IDENTITY GATES - Detail the strict 45-day post-birth mandatory registration window. Explain the systemic dependencies: why the BDRIS API requires both parents' NIDs to be digitally verified before issuing a child's certificate, and the deadlock that occurs if the parents only have legacy 13-digit NIDs.
4. SECTION 4: DOCUMENT CHECKLIST - Create separate checklists for: (a) Newborn registration (EPI card, hospital discharge slip), (b) Adult retroactive registration (SSC certificate, NID copy), and (c) Data Correction (Category-based evidence like Magistrate Affidavits vs. School transcripts).

Execute the deep research loop now. Ensure each chunk's content string stays strictly between 400 and 1500 characters and include active flags internally.

```
#### Request 2: BDRIS Fees, Processes, Rejections & Timelines
```text
Target Procedure: Bangladesh Birth & Death Registration Information System (BDRIS) - 2025/2026 Framework
Task: Execute Sections 5, 6, 7, and 8 using the locked System Instructions.

Requirements to satisfy within the content:
1. SECTION 5: FEES - Provide the exact BDT fee matrix: Free registration within 45 days, BDT 25 up to 5 years, BDT 50 for adults, and specific BDT 100-500 fees for bilingual English corrections. Document how local Ward Councilors arbitrarily inflate these fees to BDT 500-2000 [FLAG: PRACTICE_VS_POLICY].
2. SECTION 6: STEP-BY-STEP PROCESS - Map the journey from bdris.gov.bd application, UP office attestation, to physical ledger signing. Detail the "OTP limitation" where one mobile number can only be used a restricted number of times.
3. SECTION 7: REJECTION REASONS - Build recovery profiles for: (a) "Record not found" API errors when older 17-digit numbers aren't synced to the central server, and (b) Spelling mismatches with parents' NIDs. Detail the exact steps and costs to resolve them.
4. SECTION 8: TIMELINES - Contrast the LGD's advertised SLAs (e.g., 3-7 days) with the ground-truth realities of Union Parishad backlogs, server synchronization delays, and the manual signature dependencies of the UP Chairman.

Execute the deep research loop now. Output strictly as a valid JSON array.

```
#### Request 3: BDRIS Pro Tips, Fraud, Training & Dependencies
```text
Target Procedure: Bangladesh Birth & Death Registration Information System (BDRIS) - 2025/2026 Framework
Task: Execute Sections 9, 10, 11, 12, 13, and 14 using the locked System Instructions.

Requirements to satisfy within the content:
1. SECTION 9: PRO TIPS - Provide street-wisdom on how to safely navigate bdris.gov.bd server throttling and how to force a localized sync if a newly printed certificate doesn't show up on the central online verification portal.
2. SECTION 10: FRAUD WARNINGS - Expose the "Fake BRC QR Code" scams operated by cyber cafes and the extortion rings surrounding Union Parishad data-entry operators.
3. SECTION 11: TRAINING DIALOGUES - Generate 5 Bengali (চলিত ভাষা) Q&A scenarios covering: newborn registration, adult registration without hospital slips, fixing a misspelled English name, overcoming the parent-NID requirement for orphans, and identifying a fake certificate.
4. SECTION 12: DEPENDENCIES - Detail BDRIS as the absolute prerequisite for minor passports, school admissions (Primary PECE), and NID enrollment.
5. SECTION 13: CORRECTIONS & AMENDMENTS - Map the exact pathway to change a date of birth on BDRIS, detailing the Upazila Nirbahi Officer (UNO) approval bottleneck.
6. SECTION 14: SOURCE LIST - Compile the verified URLs (bdris.gov.bd) and flags used.

Execute the deep research loop now. Output strictly as a valid JSON array.

```
Are you ready to queue up the BDRIS procedure, or do you want to adjust any specific constraints before generating the next batch?



CIVIC

This is an excellent pivot. You are moving from highly structured "Top-Down" government procedures to the equally vital **"Bottom-Up" Civic & Digital Literacy module**.
In Bangladesh, knowing how to write a standard *Dorkhasto* (দরখাস্ত - formal application) or how to compress a PDF on a mobile phone to under 100KB for a government portal is just as critical as knowing the passport laws.
To keep this perfectly integrated into your **ProofSheet OpenSearch database**, we will map these everyday utilities to the exact same 10-key JSON schema and use the same chunk_type enums (mapping letters to document_checklist or training_sop, and digital tasks to procedural_guide).
Here is the three-part prompt pipeline for **Procedure 05: Everyday Civic Utilities, Document Preparation & Digital Literacy (Bangladesh)**.
### PROMPT PIPELINE: CIVIC UTILITIES & DIGITAL LITERACY
> **Where to paste:** Keep your **System Instructions** exactly as they are in Google AI Studio. Clear the chat history, and paste these three requests sequentially.
> 
#### Request 1: Bureaucratic Lexicon & Standard Letter Templates
```text
Target Procedure: Everyday Civic Utilities & Standard Document Drafting (Bangladesh — 2025/2026)
Task: Execute Sections 1, 2, and 3 using the locked System Instructions.

Conduct an exhaustive deep research sweep to map the linguistic structures, bureaucratic lexicon, and highly circulated non-governmental letter templates utilized in daily Bangladeshi civic life. Output your findings strictly as a single, continuous, valid JSON array matching the 10-key schema.

Requirements to satisfy within the content:
1. SECTION 1: THE BUREAUCRATIC LEXICON - Detail the unique "Formal-Colloquial" Bengali phrasing used in everyday administrative writing. Map out the mandatory structural elements of a standard "Dorkhasto" (দরখাস্ত): The Salutation (বরাবর), the Subject Line (বিষয়), the Formal Greeting (জনাব / সবিনয় নিবেদন এই যে), the core request, and the Formal Closing (বিনীত নিবেদক). Explain why using excessively modern/casual Bengali in these documents often results in administrative rejection or delays [FLAG: PRACTICE_VS_POLICY].
2. SECTION 2: SCHOOL & WARD COUNCILOR TEMPLATES - Generate the exact, copy-pasteable Bengali boilerplate text (with English explanations) for the two most common institutional letters: (a) A formal leave of absence/sick leave application to a School Headmaster, and (b) An application to a local Ward Councilor requesting a Character Certificate (চারিত্রিক সনদপত্র) or Heirship/Succession Certificate (ওয়ারিশান সনদ). 
3. SECTION 3: LANDLORD & POLICE (GD) TEMPLATES - Generate the exact Bengali/English boilerplate text and procedural advice for: (a) A formal 30-day notice to vacate a rental property to a Landlord (addressing common advance-deposit dispute language), and (b) A standard Police General Diary (GD) format for the loss of everyday items like a mobile phone, NID card, or academic certificate (detailing exactly what the Duty Officer expects to read to avoid harassment) [FLAG: PRACTICE_VS_POLICY].

Execute the deep research loop now. Ensure each chunk's content string stays strictly between 400 and 1500 characters and contains active inline flags.

```
#### Request 4: Digital Literacy & Document Manipulation (The "Tech Help" Guide)
```text
Target Procedure: Everyday Civic Utilities & Standard Document Drafting (Bangladesh — 2025/2026)
Task: Execute Sections 4, 5, and 6 using the locked System Instructions.

Conduct an exhaustive deep research sweep to catalog the standard digital document manipulations that non-tech-savvy citizens (or parents asking their children) must perform to interact with Bangladeshi civic portals. Output your findings strictly as a single, continuous, valid JSON array matching the 10-key schema.

Requirements to satisfy within the content:
1. SECTION 4: IMAGE TO PDF & FILE COMPRESSION - Detail the exact, step-by-step mobile-first methods to convert physical document photos (JPEGs) into PDFs. Crucially, map the workaround for the most common barrier in Bangladesh: compressing PDF and Image files to under 100KB or 2MB to bypass the rigid upload limits of portals like BDRIS, NID Wing, and e-Passport without losing text legibility.
2. SECTION 5: HANDLING ZIP, RAR, & EXCEL FILES - Write a plain-language guide (as if explaining to a non-technical parent) on how to extract ZIP/RAR files containing downloaded government forms on a standard Android device. Include steps on how to open, perform basic edits, and print Excel (.xlsx) or Word (.docx) templates distributed by local offices or employers.
3. SECTION 6: ONLINE FORM TRANSLATION & BENGALI TYPING - Detail the ground-truth friction of navigating poorly translated English-only government web forms. Provide actionable steps on using Google Translate extensions, and explain the transition from legacy Bijoy keyboard typing (বিজয়) to modern Unicode/Avro (অভ্র) phonetic typing, which is now mandatory for correctly filling out national digital portal forms [FLAG: VERIFY_2026].

Execute the deep research loop now. Ensure each chunk's content string stays strictly between 400 and 1500 characters and contains active inline flags.

```
#### Request 3: Cyber Scams, Pro Tips, and Training Dialogues
```text
Target Procedure: Everyday Civic Utilities & Standard Document Drafting (Bangladesh — 2025/2026)
Task: Execute Sections 7, 8, and 9 using the locked System Instructions.

Conduct an exhaustive deep research sweep to extract security warnings, cyber-cafe survival tips, and conversational tech-support dialogues tailored to the Bangladeshi public. Output your findings strictly as a single, continuous, valid JSON array matching the 10-key schema.

Requirements to satisfy within the content:
1. SECTION 7: PRO TIPS & CYBER CAFE SURVIVAL - Document street-level realities of relying on local cyber cafes ("কম্পিউটার দোকান") for document manipulation. Warn users about the dangers of leaving logged-in portal sessions, handing over raw NID/Passport PDFs via WhatsApp to shop owners, and the risk of USB drive malware. Provide rules for safely printing documents without compromising identity data [FLAG: PRACTICE_VS_POLICY].
2. SECTION 8: FRAUD & SCAM WARNINGS (MALICIOUS DOCUMENTS) - Expose scams targeting digitally illiterate citizens. Detail how fraudsters send malicious PDFs disguised as "Utility Bill Due Notices" or "Bank KYC Updates" via WhatsApp or email. Map the red flags of clicking unverified shortened URLs contained in unofficial SMS messages mimicking government agencies.
3. SECTION 9: SAMPLE TRAINING CONVERSATIONS - Generate exactly 5 highly realistic, warm Bengali (চলিত ভাষা) training dialogues representing a tech-savvy child ("সহায়ক") helping a parent/elder ("ব্যবহারকারী"). Scenarios must include: (1) Explaining why a passport photo won't upload (file size too big); (2) How to safely share an NID copy on WhatsApp (adding a "For Bank Use Only" watermark); (3) Walking through how to write a standard Dorkhasto for a broken streetlamp to the Ward Councilor; (4) Explaining how to open a downloaded ZIP file on an Android phone; (5) Warning them not to click a fake PDF bill link on Facebook Messenger. 

Execute the deep research loop now. Ensure each chunk's content string stays strictly between 400 and 1500 characters and contains active inline flags.

```
### Why this specific structure works for your database:
 * **Templates as Data:** By generating the *Dorkhasto* (দরখাস্ত) texts within the chunk limits, your ProofSheet app can display these exact Bengali templates to a user who searches "How do I write a letter to the police for a lost phone?"
 * **Digital Translation:** By focusing the tech sections on *mobile-first* compression and extraction, you are capturing the actual pain points of a citizen standing in a cyber cafe trying to upload a 3MB photo to a portal that only accepts 100KB.
 * **The "Child-to-Parent" Voice:** The dialogues generated in Request 3 will perfectly capture that colloquial, patient tone needed to bridge the digital divide in Bangladesh.
