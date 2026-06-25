


Role: Senior Knowledge Architect & Systems Analyst
Task: Establish the execution framework for an exhaustive civic procedure knowledge base. 

You are building a high-fidelity data repository for critical civic procedures that citizens depend on. The guiding objective is absolute ACCURACY, uncompromising COMPLETENESS, and immediate ACTIONABILITY. 

You must strictly execute your research and subsequent outputs under these three MANDATORY structural pillars:

1. EXHAUSTIVE COVERAGE (NO ABBREVIATIONS)
   - Do NOT abbreviate procedural depth, skip steps, or summarize complex requirements.
   - Capture EVERY single documented fee, processing timeline, backend rejection reason, and citizen workaround.
   - You must unearth ground-truth friction points where daily practice at the field office diverges from official ministry policy.
   - Every single data point must answer: "What actually happens on the ground, not just what the official policy claims."

2. SEMANTIC CHUNKING DISCIPLINE
   - The output MUST be formatted as valid JSON adhering strictly to the semantic_chunk schema detailed below.
   - Each chunk must map onto a distinct, logical semantic unit (e.g., legal foundations, jurisdictional maps, fee schedules).
   - Crucial Performance constraint: Keep individual chunk "content" strings strictly bounded between 400 and 1500 characters. This range is optimized for OpenSearch Serverless vector embeddings and retrieval. Do not overflow or underflow this length.

3. MANDATORY IN-PROSE FLAGGING
   - You must embed data integrity markers directly inside the text string of the content itself. Do not isolate these flags within separate metadata arrays.
   - Insert [FLAG: VERIFY_2026] directly into the prose content where facts, rules, or SLAs are prone to sudden adjustments or may have changed since the 2023 baseline.
   - Insert [FLAG: NEEDS_SOURCE] directly into the prose where primary government documentation or statutory proof cannot be verified.
   - Insert [FLAG: PRACTICE_VS_POLICY] directly into the prose where field observation or citizen reports show that official rules are ignored or altered by staff.
   - Example of correct implementation: "The official agency SLA promises a 15-day turnaround time. [FLAG: VERIFY_2026 - confirm if the central printing queue has tightened]. Ground truth: field observation and citizen reports indicate a realistic timeline of 25-45 days due to systematic server throttling."

TARGET SYSTEM SCHEMA (OPENSEARCH RETRIEVAL COMPATIBLE)
Every semantic chunk object you generate must strictly include all 10 of these keys:
{
  "chunk_id": "Unique string label following the pattern: procedure_name_N_topic",
  "chunk_type": "Must be exactly one of: legal_foundation | jurisdictional_rules | eligibility_requirements | document_checklist | fee_structure | procedural_guide | rejection_analysis | timeline_analysis | advisory | security_advisory | system_dependencies | faq | training_sop",
  "section_header": "The exact uppercase title of the template section being mapped",
  "intent_tags": ["Array of search intents like: eligibility_gate, procedural_step, rejection_fix, cost_query, timeline_query, pro_tip, fraud_warning, training"],
  "content": "The full detailed prose text with [FLAG: ...] markers embedded natively inside the sentences.",
  "key_terms_bengali": ["Array of key technical/bureaucratic terms in Bengali script"],
  "key_terms_english": ["Array of corresponding terms in English"],
  "confidence_level": "high | medium | low (based on source verification)",
  "source_urls": ["Array of primary URLs consulted during research"],
  "flags": ["Array tracking which flags were used inside the content for programmatic validation, e.g., VERIFY_2026, NEEDS_SOURCE, PRACTICE_VS_POLICY"]
}

Acknowledge understanding of these parameters. Do not truncate. Prepare to receive the target procedure definition.



Target Procedure: Bangladesh e-Passport Application, Renewal, and Data Correction (2025/2026)
Task: Execute Section 1 (LEGAL BASIS) using the Framework Mandate.

Conduct an exhaustive deep-bureaucratic research sweep regarding the statutory framework governing the target procedure. Your output must be structured strictly within the JSON schema defined in Prompt 1. 

You must research, extract, and compile the following structural components for:
SECTION 1: LEGAL BASIS

Requirements to satisfy within the content:
1. Identify the Exact Act Name, implementation year, and specific relevant sections/clauses that establish this civic procedure legally.
2. Track and document recent statutory changes, gazettes, or ministry circulars issued between 2023 and 2026. Include exact implementation dates where available. If a statutory change is highly prone to updates, apply the [FLAG: VERIFY_2026] tag directly next to the fact.
3. Map the complete Authority Hierarchy. Clearly delineate which Ministry, Directorate General, or Department holds primary execution power, which bodies hold subordinate administrative roles, and how enforcement authority cascades down to the regional field offices.
4. Detail any hidden or overriding notifications, rules, or temporary regulations that legally supersede earlier versions of the primary Act.

Data Integrity Constraints:
- Every statutory assertion must be backed by formal legal naming conventions and specific dates. 
- If your deep search cannot confirm the precise legal section or primary statutory reference for an operational policy, you must explicitly flag it in the prose as [FLAG: NEEDS_SOURCE].
- Maintain a warm, highly informative, yet authoritative tone. Do not write like a cold, ambiguous government circular; explain to the citizen exactly *why* these laws establish the boundaries of their application.
- Ensure the chunk size stays strictly between 400 and 1500 characters.

Output the results inside a valid, un-truncated JSON array matching the Prompt 1 specifications.



Target Procedure: Bangladesh e-Passport Application, Renewal, and Data Correction (2025/2026)
Task: Execute Section 2 (ISSUING AUTHORITY MATRIX) using the Framework Mandate.

Conduct an exhaustive deep research sweep to map out the complete, ground-truth operational footprint of the Department of Immigration and Passports (DIP) in Bangladesh. Your output must be structured strictly within the JSON schema defined in Prompt 1.

You must research, extract, and compile the following structural components for:
SECTION 1: LEGAL BASIS (re-verify context if necessary) and primarily SECTION 2: ISSUING AUTHORITY MATRIX

Requirements to satisfy within the content:
1. Provide a complete geographic jurisdictional breakdown of Regional Passport Offices (RPOs) across all divisions.
2. Unearth and document official office addresses, active contact phone numbers, and actual operating hours for public services (biometric enrollment vs. delivery windows).
3. Clearly define the sorting rules specifying exactly which applicant type (e.g., first-time adult, minor, re-issue with changes, government/official passport holder, diaspora/dual-citizen) is assigned to which specific office type or counter, leaving zero ambiguity.
4. Provide comprehensive, hyper-specific Dhaka-specific details. Map out the overlapping jurisdictions of Agargaon, Uttara, Jatrabari, Dhaka Cantonment, and Bangladesh Secretariat RPOs. Detail exactly which Thanas/police stations filter into each of these sub-offices.

Data Integrity & Lived-Experience Constraints:
- Ground-Truth Queues: Do not just paste the official office hours. Note the actual ground-truth timing when citizens begin lining up outside the gates. Use the [FLAG: PRACTICE_VS_POLICY] tag when explaining actual operating/gate-closing hours versus advertised schedules.
- If specific RPO contact phone numbers or operating changes since the 2025/2026 updates cannot be firmly verified via official DIP channels, you must explicitly flag it in the prose as [FLAG: NEEDS_SOURCE].
- Use the [FLAG: VERIFY_2026] tag next to any localized jurisdictional realignment or newly opened sub-offices in the Dhaka metro area.
- Keep the narrative clear, easily navigable, and highly informative for a citizen attempting to identify their correct physical venue.
- Ensure each chunk's content string stays strictly between 400 and 1500 characters.

Output the results inside a valid, un-truncated JSON array matching the Prompt 1 specifications.



Target Procedure: Bangladesh e-Passport Application, Renewal, and Data Correction (2025/2026)
Task: Execute Section 3 (ELIGIBILITY & IDENTITY GATES) using the Framework Mandate.

Conduct an exhaustive deep research sweep to analyze the strict eligibility criteria, age constraints, and digital identity prerequisites required to clear the entry gates for a Bangladesh e-Passport. Your output must be structured strictly within the JSON schema defined in Prompt 1.

You must research, extract, and compile the following structural components for:
SECTION 3: ELIGIBILITY & IDENTITY GATES

Requirements to satisfy within the content:
1. Define the precise age brackets determining passport passport booklet validity (e.g., under 18 gets 5-year maximum validity, adults 18–65 eligible for 10-year validity, over 65 capped at 5 years) and explain the corresponding identity requirements.
2. Outline all documented disqualifying conditions that block issuance, such as active criminal litigation, court-ordered travel bans, financial/banking default flags, or duplicate biometric matches.
3. Detail the absolute structural identity document dependencies. Explain exactly WHY the national e-Passport database links directly to the Election Commission's NID database or the BDRIS birth certificate database for real-time validation. Highlight what causes a system-level mismatch at the registration gate.
4. Meticulously detail the rules governing special applicant classes: minors (including parental NID requirements), government servants/autonomous body employees (NOC/GO requirements), and the diaspora (Non-Resident Bangladeshis applying via overseas foreign missions).

Data Integrity & Lived-Experience Constraints:
- Use the [FLAG: PRACTICE_VS_POLICY] tag when explaining how passport offices handle parents with missing or un-digitized NIDs when registering a minor, or how field offices handle government employees missing a verified digital NOC.
- Apply the [FLAG: VERIFY_2026] tag to any new biometric gates, automated facial recognition checks (AFIS/ABIS thresholds), or recent age restriction shifts enforced in the current 2026 pipeline.
- If the exact operational parameters for security clearances or state disqualifications are unverified via primary ministry sources, flag them explicitly as [FLAG: NEEDS_SOURCE].
- Maintain an encouraging, warm, and clear tone that breaks down complex identity dependencies into actionable knowledge for the user.
- Ensure each chunk's content string stays strictly between 400 and 1500 characters.

Output the results inside a valid, un-truncated JSON array matching the Prompt 1 specifications.




Target Procedure: Bangladesh e-Passport Application, Renewal, and Data Correction (2025/2026)
Task: Execute Section 4 (DOCUMENT CHECKLIST) using the Framework Mandate.

Conduct an exhaustive deep research sweep to map out every single mandatory, conditional, and supporting document required for an e-Passport application. Your output must be structured strictly within the 10-key JSON schema defined in Prompt 1.

You must research, extract, and compile separate, distinct document checklists for the following structural components:
SECTION 4: DOCUMENT CHECKLIST (BY APPLICATION TYPE)

Requirements to satisfy within the content:
1. First-Time Adult Path: Detail the exact requirements for a standard adult applicant (Printed summary, appointment slip, original NID, bank e-Challan receipt).
2. Renewal / Re-issue Path: Detail what a citizen must bring when transitioning from a legacy MRP or renewing an expired e-Passport (Surrender of old original passport, bio-data page photocopies).
3. The "Samsodhoni" (Data Correction) Path: List the absolute documentary chain required to execute demographic modifications (Original NID/BRC matching the change, the mandatory signed Self-Declaration/Ongikarnama, and supporting evidence like SSC/HSC certificates or Nikahnama/Talaknama for name shifts).
4. Minors Under 18 Path: Detail parent-child document linkages (Child’s 17-digit English BRC, originals and photocopies of BOTH parents' NIDs). Specify the rules for minors under 6 who bypass live biometrics (3R-sized photos with gray/white backgrounds).
5. Government / Official Path: List the exact verification documents required for priority processing (GO or portal-uploaded digital NOC).

Data Integrity & Lived-Experience Constraints:
- Original vs. Photocopy: For every document listed, explicitly state whether the counter clerk requires the original, a standard photocopy, or an officially attested copy.
- Document Deficiencies: Document the leading "gotchas" that cause immediate rejection at Counter 1 (e.g., bringing a parents' NID photocopy instead of the original, or a BRC that is only in Bengali).
- Use the [FLAG: PRACTICE_VS_POLICY] tag when noting instances where front-desk clerks illegally demand extra documents (like utility bills or magistrate affidavits) that violate central DIP circulars.
- Apply the [FLAG: VERIFY_2026] tag to any new digital document verification layers added to the gate system this year.
- Ensure each chunk's content string stays strictly between 400 and 1500 characters.

Output the results inside a valid, un-truncated JSON array matching the Prompt 1 specifications.




Target Procedure: Bangladesh e-Passport Application, Renewal, and Data Correction (2025/2026)
Task: Execute Section 5 (FEES) using the Framework Mandate.

Conduct an exhaustive deep research sweep to map out the entire financial structure, taxation layers, payment channels, and penalty matrix for e-Passport processing. Your output must be structured strictly within the 10-key JSON schema defined in Prompt 1.

You must research, extract, and compile the following structural components for:
SECTION 5: FEES (COMPLETE)

Requirements to satisfy within the content:
1. Meticulous BDT Fee Mapping: Document the exact fee amounts in Bangladeshi Taka (BDT) for all available service tiers. Never use vague terms like "nominal fee" or "standard charges." Break them down rigidly by:
   - 48 Pages vs. 64 Pages booklet size.
   - 5 Years vs. 10 Years validity.
   - Delivery Tiers: Regular (15-21 working days) vs. Express (7-10 working days) vs. Super Express (2 working days).
2. Surcharges & Taxes: Explicitly state the Government VAT percentage (e.g., 15% VAT included or added) and any supplementary institutional charges (such as the 10% Wage Earners' Welfare Fund surcharge levied at overseas foreign missions).
3. Payment Portals & Financial Venues: Detail the precise online payment gateways authorized by the state (EkPay, DGePay, ShurjoPay, Sonali Bank online) and specify the offline A-Challan bank ecosystem. List every commercial bank legally permitted to accept offline passport challans (e.g., Sonali, Bank Asia, Premier Bank, Dhaka Bank, One Bank, Trust Bank).
4. Penalties & Corrections: Detail the pricing updates or secondary fees required for executing a "Samsodhoni" (data correction) or replacing a lost/stolen passport. Document the exact late penalty formulas or the requirement to pay full original fees if an application is abandoned.

Data Integrity & Lived-Experience Constraints:
- Use the [FLAG: CHECK FOR 2026 UPDATE] or [FLAG: VERIFY_2026] tags next to every listed fee tier to flag potential adjustments made by the Ministry of Finance for the current fiscal cycle.
- Document systemic payment failures. Use the [FLAG: PRACTICE_VS_POLICY] tag to highlight ground-truth instances where online gateway deductions occur but fail to generate a digital receipt, forcing citizens to pay twice or wait 24-48 hours for API reconciliation.
- Ensure each chunk's content string stays strictly between 400 and 1500 characters.

Output the results inside a valid, un-truncated JSON array matching the Prompt 1 specifications.




Target Procedure: Bangladesh e-Passport Application, Renewal, and Data Correction (2025/2026)
Task: Execute Section 6 (STEP-BY-STEP PROCESS) using the Framework Mandate.

Conduct an exhaustive deep research sweep to chronicle every individual step an applicant must execute from the initial decision to final passport collection. Your output must be structured strictly within the 10-key JSON schema defined in Prompt 1.

You must research, extract, and compile the following structural components for:
SECTION 6: STEP-BY-STEP PROCESS (GROUND TRUTH EDITION)

Requirements to satisfy within the content:
Meticulously map out the procedural timeline across all primary phases, including:
1. Online Registration & Portal Dynamics (Form completion, handling account creation, and server behavior).
2. Document Upload Protocols (Standardization of formats, handling metadata or size limitations).
3. Payment Processing Routing (Gateway selections, challan verification, and systemic transaction routing).
4. Physical Appointment Booking (Inventory management of slots, resetting times, and booking windows).
5. Biometric Enrollment Day (Arrival protocols, physical staging/queues, photo/fingerprint/iris capture booths, and tracking slips).
6. Post-Enrollment Backend Verification (The routing of files through automated identity checks and central printing queues).
7. Physical Passport Collection (Notification alerts, counter assignments, and identity verification upon delivery).

For EACH separate step identified across these phases, you must explicitly sub-delineate:
   a) Official Expectation (What the government says should happen under ideal conditions).
   b) Ground Truth (What actually happens based on field observations, forum complaints, and citizen tracking).
   c) Common Failure Points (The exact reasons a step crashes, stalls, or causes an administrative lock).
   d) Workarounds (The precise, street-level actions an applicant can take to bypass or resolve the error).

Data Integrity & Lived-Experience Constraints:
- Meticulously target systemic friction points: portal throttling during peak traffic, server downtime between 23:00 and 06:00, photo booth queue dynamics, and lower-tier staff discretion.
- You must embed the [FLAG: PRACTICE_VS_POLICY] tag inside the prose text of any step where actual field operations or server uptime realities conflict with official ministerial guidelines.
- Use the [FLAG: VERIFY_2026] tag to note recent digitization updates, portal interface re-designs, or shifts in backend automated approval flows introduced for the 2026 issuance pipeline.
- Ensure each chunk's content string stays strictly between 400 and 1500 characters.

Output the results inside a valid, un-truncated JSON array matching the Prompt 1 specifications.



Target Procedure: Bangladesh e-Passport Application, Renewal, and Data Correction (2025/2026)
Task: Execute Section 7 (REJECTION REASONS & EXACT FIXES) using the Framework Mandate.

Conduct an exhaustive deep research sweep to identify, catalog, and analyze every major reason an e-Passport application is rejected, paused, or frozen. Your output must be structured strictly within the 10-key JSON schema defined in Prompt 1.

You must research, extract, and compile the following structural components for:
SECTION 7: REJECTION REASONS & EXACT FIXES

Requirements to satisfy within the content:
Identify and detail every common rejection reason, including but not limited to:
1. NID/BRC Data Collision (System-level demographic mismatches).
2. AFIS/ABIS Biometric Match Collision (Fingerprint/iris matching a previous, undeclared MRP or e-Passport).
3. Localized Address Mismatch or Jurisdictional Boundary Error during submission.
4. Missing or Un-uploaded Digital NOC/GO for government employees.
5. Inconsistent Transliteration/Spelling on secondary matching documents (e.g., Nikahnama or educational certificates).

For EACH common rejection reason identified, you must explicitly detail:
   a) Root Cause (Why the system or officer triggers the rejection/hold).
   b) Detection Stage (Where exactly in the pipeline it is caught—e.g., Counter 1 screening, data entry, backend biometric processing, printing queue).
   c) Exact Remedial Steps (A granular, step-by-step recovery guide for the citizen).
   d) Fix Timeline (Expressed explicitly in working days, not vague ranges).
   e) Fix Cost (Expressed as an exact BDT figure for administrative or processing fees).
   f) Salvageability (Clear statement on whether the original application/payment can be salvaged or if the citizen must abandon it and restart from scratch).

Data Integrity & Lived-Experience Constraints:
- Provide exact bureaucratic terms and form names where applicable (e.g., "AFIS/ABIS Rejected Ongikarnama" / আফিস/এবিস বাতিলকৃত অঙ্গীকারনামা).
- Highlight hidden operational choke points. Use the [FLAG: PRACTICE_VS_POLICY] tag where passport offices fail to publicize existing resolution procedures (such as Counter 3 identity merging) or let applications freeze indefinitely without informing the applicant via SMS.
- Apply the [FLAG: VERIFY_2026] tag to any new automated rejection rules or updated fee schedules for data reconciliation implemented in 2026.
- Ensure each chunk's content string stays strictly between 400 and 1500 characters.

Output the results inside a valid, un-truncated JSON array matching the Prompt 1 specifications.



================================================================================
PART 1: CRITICAL INSTRUCTIONS & RETRIEVAL FRAMEWORK MANDATE
================================================================================
Role: Senior Knowledge Architect & Systems Analyst
Task: Execute an exhaustive civic procedure deep-dive report.

You are constructing a high-fidelity data repository for critical civic procedures. The guiding objective is absolute ACCURACY, uncompromising COMPLETENESS, and immediate ACTIONABILITY. You must strictly execute your research and subsequent outputs under these three MANDATORY structural pillars:

1. EXHAUSTIVE COVERAGE (NO ABBREVIATIONS)
   - Do NOT abbreviate procedural depth, skip steps, or summarize complex requirements.
   - Capture EVERY single documented fee, processing timeline, backend rejection reason, and citizen workaround.
   - Unearth ground-truth friction points where daily practice at the field office diverges from official ministry policy (e.g., undocumented speed money or localized administrative processing inflation).
   - Every single data point must answer: "What actually happens on the ground, not just what the official policy claims."

2. SEMANTIC CHUNKING DISCIPLINE
   - The output MUST be formatted as valid JSON adhering strictly to the semantic_chunk schema detailed below.
   - Each chunk must map onto a distinct, logical semantic unit.
   - Crucial Performance constraint: Keep individual chunk "content" strings strictly bounded between 400 and 1500 characters. This range is optimized for vector embeddings and retrieval. Do not overflow or underflow this length.

3. MANDATORY IN-PROSE FLAGGING
   - You must embed data integrity markers directly inside the text string of the content itself. Do not isolate these flags within separate metadata arrays.
   - Insert [FLAG: VERIFY_2026] directly into the prose content where facts, rules, or SLAs are prone to sudden adjustments or may have changed recently.
   - Insert [FLAG: NEEDS_SOURCE] directly into the prose where primary government documentation or statutory proof cannot be verified.
   - Insert [FLAG: PRACTICE_VS_POLICY] directly into the prose where field observation or citizen reports show that official rules are ignored, throttled, or altered by staff.

TARGET SYSTEM SCHEMA (OPENSEARCH RETRIEVAL COMPATIBLE)
Every semantic chunk object you generate must strictly include all 10 of these keys:
{
  "chunk_id": "Unique string label following the pattern: procedure_name_N_topic",
  "chunk_type": "Must be exactly one of: legal_foundation | jurisdictional_rules | eligibility_requirements | document_checklist | fee_structure | procedural_guide | rejection_analysis | timeline_analysis | advisory | security_advisory | system_dependencies | faq | training_sop",
  "section_header": "The exact uppercase title of the template section being mapped",
  "intent_tags": ["Array of search intents like: eligibility_gate, procedural_step, rejection_fix, cost_query, timeline_query, pro_tip, fraud_warning, training"],
  "content": "The full detailed prose text with [FLAG: ...] markers embedded natively inside the sentences.",
  "key_terms_bengali": ["Array of key technical/bureaucratic terms in Bengali script"],
  "key_terms_english": ["Array of corresponding terms in English"],
  "confidence_level": "high | medium | low (based on source verification)",
  "source_urls": ["Array of primary URLs consulted during research"],
  "flags": ["Array tracking which flags were used inside the content for programmatic validation, e.g., VERIFY_2026, NEEDS_SOURCE, PRACTICE_VS_POLICY"]
}

================================================================================
PART 2: CURRENT TARGET TASK — SECTION 8: REALISTIC TIMELINES
================================================================================
Target Procedure: Bangladesh e-Passport Application, Renewal, and Data Correction (2025/2026)
Task: Execute Section 8 (REALISTIC TIMELINES) using the Framework Mandate above.

Conduct an exhaustive deep research sweep to map out the true temporal dynamics of the e-Passport pipeline, contrasting administrative advertising with real-world operational speeds. Your output must be structured strictly within the 10-key JSON schema defined in Part 1.

You must research, extract, and compile the following structural components for:
SECTION 8: REALISTIC TIMELINES (Official vs. Ground Truth)

Requirements to satisfy within the content:
For each distinct service tier available (Regular, Express, and Super Express), you must comprehensively evaluate and record:
   a) Official SLA: Document the exact processing times publicly advertised by the Department of Immigration and Passports (DIP) or Ministry circulars.
   b) Ground Truth Timeline: Unearth the true, citizen-reported operational timelines observed in the field across late 2024, 2025, and the current 2026 pipeline. 
   c) Extraneous Delays: Identify what specific technical, political, or infrastructural variables cause compounding delays completely outside the applicant's control (e.g., centralized personalization print-queue overflows, physical booklet/chip shortages, or backend database synchronization drops).
   d) Official Expediting Actions: List any legitimate, legal protocols an applicant can execute to accelerate a stalled application (such as filing a formal written appeal with the RPO Assistant Director or leveraging verified urgent medical/educational justifications).
   e) The Sovereign Bottleneck Stage: Pinpoint exactly which step in the entire journey is statistically responsible for the longest, most frequent processing stalls (e.g., backend biometric profile reconciliation, regional office delivery sorting, or automated background API validation freezes).

Data Integrity & Lived-Experience Constraints:
- Use the [FLAG: VERIFY_2026] tag directly within your prose text when noting instances where timelines have genuinely improved or tightened due to recent database migrations, portal optimization updates, or the structural relaxation of manual clearances.
- Apply the [FLAG: PRACTICE_VS_POLICY] tag inside the sentences of any service tier where the ground-truth velocity radically diverges from advertised SLAs—specifically highlighting the "Super Express" tier anomalies where backend data corrections or biometric exceptions automatically strip away the 48-hour delivery promise.
- Ensure each chunk's content string stays strictly between 400 and 1500 characters.

Execute the deep research loop now and output the results inside a single, valid, un-truncated JSON array matching the specification. Do not include markdown text wrappers outside of the valid JSON object array.



Target Procedure: Bangladesh e-Passport Application, Renewal, and Data Correction (2025/2026)
Task: Execute Section 9 (PRO TIPS FOR CITIZENS) using the established Framework Mandate.

Conduct an exhaustive deep research sweep to compile street-level wisdom, insider operational knowledge, and practical advice that citizens use to navigate the e-Passport process efficiently. Your output must be structured strictly within the 10-key JSON schema established in this thread.

You must research, extract, and compile the following structural components for:
SECTION 9: PRO TIPS FOR CITIZENS

Requirements to satisfy within the content:
1. Insider Knowledge & Time-Savers: Document the exact times of day when the online portal (epassport.gov.bd) experiences the least server throttling (e.g., navigating late night/early morning vs. peak business hours) and the precise hour daily appointment inventories reset.
2. Office-Specific Anomalies: Identify which specific Dhaka Metropolitan or divisional Regional Passport Offices (RPOs) are notoriously congested, and share tactical advice on navigating their specific physical queues (e.g., when to line up at the gate).
3. Managing Staff Discretion: Provide actionable advice on how a citizen should handle informal administrative friction at the front desk (e.g., what to do when a screening officer incorrectly demands a utility bill or affidavit that violates the recent Ministry circulars).
4. Seasonal Surges to Avoid: Detail the worst times of the year to apply (e.g., the Hajj season rush, post-SSC/HSC result surges, or periods following major policy announcements) when processing SLAs historically collapse.
5. Critical Error Avoidance: Outline the most common, irreversible data-entry mistakes citizens make during the online form submission phase that force them to abandon their application fee and start over.

Data Integrity & Lived-Experience Constraints:
- Differentiate clearly between legitimate, officially sanctioned expediting options (like medical emergencies) and unofficial/informal networks. 
- Use the [FLAG: PRACTICE_VS_POLICY] tag when explaining how citizens use street-level workarounds to bypass rigid queue systems or counter rejections.
- Apply the [FLAG: VERIFY_2026] tag to any new digital queue management systems, appointment tracking methods, or portal updates introduced recently.
- Ensure each chunk's content string stays strictly between 400 and 1500 characters.

Execute the deep research loop now and output the results inside a single, valid, un-truncated JSON array matching the specification. Do not include markdown text wrappers outside of the valid JSON object array.



Target Procedure: Bangladesh e-Passport Application, Renewal, and Data Correction (2025/2026)
Task: Execute Section 10 (FRAUD & SCAM WARNINGS) using the established Framework Mandate.

Conduct an exhaustive deep research sweep to identify, catalog, and expose the fraudulent operations, predatory middleman (Dalal) schemes, and digital scams targeting passport applicants. Your output must be structured strictly within the 10-key JSON schema established in this thread.

You must research, extract, and compile the following structural components for:
SECTION 10: FRAUD & SCAM WARNINGS

Requirements to satisfy within the content:
For each distinct scam or extortion method identified (such as the "Super Express Dalal Scam," fake online passport helper portals, or biometric queue-jumping rings), you must explicitly detail:
   a) Scam Description: Define the precise mechanisms of the deceptive practice and the false promises used to trap victims.
   b) Perpetrators: Identify who commits the fraud (e.g., physical brokers operating outside gates, corrupt lower-tier counter staff, third-party cyber-cafe operators, or malicious online actors).
   c) Specific Extortion Rates: Provide exact BDT currency figures or price ranges typically extracted from victims (never use vague phrases like "high costs").
   d) Applicant Losses: List the precise damages sustained by the victim, focusing on financial loss, identity data exposure, forfeited government fees, or severe application processing delays.
   e) Red Flags & Recognition Patterns: Outline explicit warning signs that citizens must observe to instantly recognize the scam.
   f) Official Reporting Mechanisms: Detail the formal grievance channels, anti-corruption portals, or ministry hotlines available to report the fraud.

Data Integrity & Lived-Experience Constraints:
- Clearly distinguish between illegal/predatory scams, unofficial but tolerated field shortcuts (like tipping cyber cafes for error-free PDF formatting), and legitimate paid services (like using bank agents for e-Challan generation).
- Use the [FLAG: PRACTICE_VS_POLICY] tag when detailing instances where front-desk staff or security personnel actively collude with or ignore middleman networks operating on RPO premises.
- Apply the [FLAG: NEEDS_SOURCE] tag if an official enforcement pathway or government agent registry cannot be verified through active 2026 DIP records.
- Ensure each chunk's content string stays strictly between 400 and 1500 characters.

Execute the deep research loop now and output the results inside a single, valid, un-truncated JSON array matching the specification. Do not include markdown text wrappers outside of the valid JSON object array.



Target Procedure: Bangladesh e-Passport Application, Renewal, and Data Correction (2025/2026)
Task: Execute Section 11 (SAMPLE TRAINING CONVERSATIONS) using the established Framework Mandate.

Conduct an exhaustive deep research sweep to generate high-fidelity, conversationally natural training dialogues in Bengali. These scenarios will train AI systems to support citizens dealing with real-world passport hurdles. Your output must be structured strictly within the 10-key JSON schema established in this thread.

You must research, extract, and compile the following structural components for:
SECTION 11: SAMPLE TRAINING CONVERSATIONS (BENGALI)

Requirements to satisfy within the content:
Generate exactly 5 distinct, highly realistic Bengali Q&A scenarios. Each scenario must use specific form names, counter numbers, correct fee amounts, and the actual procedural rules updated for the 2025/2026 framework. The scenarios must cover:
   1. Simple/Beginner Scenario: Navigating a basic first-time application or straightforward online fee payment.
   2. Complex/Delayed Scenario: Handling an un-notified processing freeze at the backend personalization or central print-queue level.
   3. Mistake-Recovery Scenario: Resolving a critical typo discovered post-submission or bypassing a system-level gateway rejection.
   4. Special-Case Scenario: Navigating passport enrollment for a minor child, elderly relative, or a Non-Resident Bangladeshi (NRB) applying from abroad.
   5. Fraud-Prevention Scenario: Educating an applicant on how to spot and safely reject a broker's false "2-day Super Express delivery" promise.

Data Integrity & Tone Constraints:
- Format each dialogue strictly using the text tags: "ব্যবহারকারী: [Question]" and "সহায়ক: [Response]".
- The responses from the helper ("সহায়ক") must be written in warm, plain, conversational Bengali (চলিত ভাষা). Avoid cold, rigid, bureaucratic terminology; ensure it reads like a helpful peer explaining the street-level path to a citizen.
- You must embed the mandatory integrity flags (`[FLAG: PRACTICE_VS_POLICY]`, `[FLAG: VERIFY_2026]`, or `[FLAG: NEED_SOURCE]`) directly inside the conversational responses of the "সহায়ক" where the advice accounts for operational anomalies or recent policy changes (e.g., the 2025 police verification waiver).
- Ensure each chunk's content string stays strictly between 400 and 1500 characters.

Execute the deep research loop now and output the results inside a single, valid, un-truncated JSON array matching the specification. Do not include markdown text wrappers outside of the valid JSON object array.




Target Procedure: Bangladesh e-Passport Application, Renewal, and Data Correction (2025/2026)
Task: Execute Section 12 (RELATED PROCEDURES & DEPENDENCIES) using the established Framework Mandate.

Conduct an exhaustive deep research sweep to map out the interconnected matrix of upstream and downstream civic procedures that the e-Passport system depends on. Your output must be structured strictly within the 10-key JSON schema established in this thread.

You must research, extract, and compile the following structural components for:
SECTION 12: RELATED PROCEDURES & DEPENDENCIES

Requirements to satisfy within the content:
Identify and diagram every external public administrative procedure connected to passport issuance (encompassing NID corrections, BDRIS birth certificate digitizations, Ministry of Foreign Affairs e-Apostille attestations, Police Clearance Certificate procurement, and Dual Nationality Certificate processing). For each distinct connection, you must explicitly detail:
   a) Core Integration Variable: Explain exactly why the systems are connected and what specific datasets or cryptographic tokens are shared across the ministry boundaries.
   b) Chronological Sequencing: Define the mandatory, legally enforced sequence of execution (e.g., stating definitively which document must be corrected first before the next system gate will open).
   c) Cascading Hidden Delays: Meticulously document the hidden processing lag times embedded within upstream procedures. Highlight how an administrative delay in one agency (such as a 20-to-60-day backlog at the Election Commission for NID edits) completely paralyzes the downstream passport timeline.
   d) Cross-Referenced Evidentiary Demands: Detail the precise document formatting and spelling dependencies that must match perfectly across all linked platforms to prevent automated system rejections.

Data Integrity & Lived-Experience Constraints:
- Critically focus on the structural "choke points" where citizens lose months because they did not complete prerequisites in advance.
- You must embed the [FLAG: PRACTICE_VS_POLICY] tag inside the prose where official multi-agency data synchronization promises differ from the real-world manual verification delays reported by citizens.
- Use the [FLAG: VERIFY_2026] tag to note recent API stabilization measures or centralized database integration overhauls deployed this year to connect DIP with BDRIS or the NID registries.
- Ensure each chunk's content string stays strictly between 400 and 1500 characters.

Execute the deep research loop now and output the results inside a single, valid, un-truncated JSON array matching the specification. Do not include markdown text wrappers outside of the valid JSON object array.



Target Procedure: Bangladesh e-Passport Application, Renewal, and Data Correction (2025/2026)
Task: Execute Section 13 (CORRECTIONS & AMENDMENTS) using the established Framework Mandate.

Conduct an exhaustive deep research sweep to analyze the post-issuance modification pathways, document correction protocols, and structural data adjustments allowed after an e-Passport booklet has been legally printed. Your output must be structured strictly within the 10-key JSON schema established in this thread.

You must research, extract, and compile the following structural components for:
SECTION 13: CORRECTIONS & AMENDMENTS (IF APPLICABLE)

Requirements to satisfy within the content:
1. Post-Issuance Error Resolution: Detail the precise administrative steps a citizen must take if they discover a typographical or data error *after* receiving their physical passport booklet. Delineate when the DIP assumes financial liability (printing error) versus when the citizen must pay for a full re-issue (data entry error).
2. Marital Status Amendments: Meticulously detail the documentary and legal requirements for changing marital status (adding a spouse's name post-marriage or executing data removals post-divorce). Define the strict transliteration matching required against the original Nikahnama or Talaknama.
3. Legal Sovereignty Thresholds: Delineate which specific demographic corrections can be executed via self-service portal pathways versus those that strictly require a first-class magistrate's notarized affidavit, educational board verification, or an official decree from a civil court.
4. Post-Amendment Revalidation: Outline the backend database updates, cryptographic chip re-writes, or mandatory notification routines to overseas embassies required to ensure the amended identity flows correctly into global immigration verification networks.

Data Integrity & Lived-Experience Constraints:
- If this procedure does not permit any manual post-issuance amendments without forcing a complete technical re-application and new biometric enrollment fee, state that restriction explicitly.
- Use the [FLAG: PRACTICE_VS_POLICY] tag when exposing regional office resistance to marital data updates or cases where consular clerks reject valid foreign marriage deeds.
- Apply the [FLAG: VERIFY_2026] tag to any new digital amendment policies, online e-Apostille alignment updates, or revised circular mandates implemented during the current fiscal year.
- Ensure each chunk's content string stays strictly between 400 and 1500 characters.

Execute the deep research loop now and output the results inside a single, valid, un-truncated JSON array matching the specification. Do not include markdown text wrappers outside of the valid JSON object array.
