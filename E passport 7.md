[
{
"chunk_id": "epassport_7_nid_brc_collision",
"chunk_type": "rejection_analysis",
"section_header": "REJECTION REASONS & EXACT FIXES",
"intent_tags": [
"rejection_fix",
"procedural_step",
"fraud_warning"
],
"content": "NID/BRC Data Collisions remain the primary cause for immediate application rejection. The Root Cause stems from systemic demographic mismatches—such as the abbreviation of 'Mohammed' to 'Md.', age discrepancies, or misaligned parental names—between the applicant's legacy passport and their foundational NID or 17-digit English BRC. Detection Stage: This is almost universally caught at Counter 1 during primary document screening. Exact Remedial Steps: The citizen must execute a formal 'Samsodhoni' (data correction) application. This requires submitting a manually signed 'Ongikarnama' (Self-Declaration Form) assuming legal liability, alongside the original NID/BRC and supporting educational certificates (like SSC/HSC). Fix Timeline: Even if the Super Express tier is selected, data mismatch reconciliations mandate manual backend reviews, extending the timeline to a strict 15 to 21 working days. Fix Cost: The applicant must pay the absolute full original fee (e.g., TK 4,025 for a standard 48-page, 5-year booklet). Salvageability: If the citizen submitted the online form and paid via EkPay with the wrong data, the application cannot be salvaged. The fee is entirely non-refundable, and the applicant must completely restart from scratch. [FLAG: VERIFY_2026 - confirm if the portal update now allows partial demographic editing post-payment without forcing a total forfeit].",
"key_terms_bengali": [
"তথ্য সংশোধন",
"অঙ্গীকারনামা",
"ভুল তথ্য"
],
"key_terms_english": [
"Data Collision",
"Samsodhoni",
"Self-Declaration Form"
],
"confidence_level": "high",
"source_urls": [
"https://passport.feni.gov.bd/pages/static-pages/69912e34516a96d4de40990e",
"https://passport.brahmanbaria.gov.bd/pages/notices/6990c179ba9bb75677b7de46"
],
"flags": [
"VERIFY_2026"
]
},
{
"chunk_id": "epassport_7_afis_abis_collision",
"chunk_type": "rejection_analysis",
"section_header": "REJECTION REASONS & EXACT FIXES",
"intent_tags": [
"rejection_fix",
"security_advisory",
"system_dependencies"
],
"content": "The most severe administrative freeze occurs due to an AFIS/ABIS Biometric Match Collision. The Root Cause is triggered when the Automated Biometric Identification System (ABIS) detects that the applicant's live 10-fingerprint or iris scan matches a previously issued, undeclared Machine Readable Passport (MRP) or e-Passport, typically associated with age or identity manipulation. Detection Stage: This is caught exclusively during the Post-Enrollment Backend Verification phase. Exact Remedial Steps: Citizens must download and physically submit a highly specific document titled 'AFIS/ABIS Rejected আইডি যাচাই সংক্রান্ত অঙ্গীকারনামা (ফরম)' (AFIS/ABIS Rejected Identity Verification Self-Declaration Form). They must then secure an in-person clearance hearing with the Assistant Director (AD) at the RPO. [FLAG: PRACTICE_VS_POLICY] While official policy dictates a transparent resolution matrix, ground-truth operations reveal that the DIP rarely informs applicants via SMS when a biometric freeze occurs; files simply stall indefinitely under 'Pending Backend Verification' until the citizen physically investigates. Fix Timeline: Resolution varies wildly but practically spans 30 to 60 working days due to intense manual scrutiny. Fix Cost: Re-application requires the standard full fee (e.g., TK 4,025 to TK 10,350). Salvageability: The current application is completely frozen until the AD formally clears the legacy biometric conflict from the central server.",
"key_terms_bengali": [
"আফিস/এবিস বাতিলকৃত",
"আইডি যাচাই",
"বায়োমেট্রিক তথ্য"
],
"key_terms_english": [
"AFIS/ABIS Rejected",
"Biometric Match Collision",
"Pending Backend Verification"
],
"confidence_level": "high",
"source_urls": [
"https://dip.gov.bd/pages/forms/6922d9fa933eb65569e0180d",
"https://passport.pabna.gov.bd/pages/notices/afis-abis-rejected-multiple-active-mrp-%E0%A6%86%E0%A6%87%E0%A6%A1%E0%A6%BF-%E0%A6%AF%E0%A6%BE%E0%A6%9A%E0%A6%BE%E0%A6%87-%E0%A6%B8%E0%A6%82%E0%A6%95%E0%A7%8D%E0%A6%B0%E0%A6%BE%E0%A6%A8%E0%A7%8D%E0%A6%A4-%E0%A6%85%E0%A6%99%E0%A7%8D%E0%A6%97%E0%A7%80%E0%A6%95%E0%A6%BE%E0%A6%B0%E0%A6%A8%E0%A6%BE%E0%A6%AE%E0%A6%BE-%E0%A6%AB%E0%A6%B0%E0%A6%AE-5b80bd-697f6ccc35ce18e1c06ac67e"
],
"flags": [
"PRACTICE_VS_POLICY"
]
},
{
"chunk_id": "epassport_7_address_jurisdiction_error",
"chunk_type": "rejection_analysis",
"section_header": "REJECTION REASONS & EXACT FIXES",
"intent_tags": [
"rejection_fix",
"procedural_step",
"eligibility_gate"
],
"content": "A pervasive systemic trap is the Localized Address Mismatch or Jurisdictional Boundary Error. The Root Cause is that the e-Passport backend algorithm strictly locks an applicant's biometric enrollment to the Regional Passport Office (RPO) governing their 'Present Address' Thana (Police Station). For instance, a citizen residing in Badda Thana must apply at Dhaka East (Aftabnagar), while someone in Mirpur must apply at Agargaon. Detection Stage: Caught instantly at the front-desk screening counter when the clerk cross-references the online summary sheet against the physical address proofs. Exact Remedial Steps: The applicant must completely abandon the misrouted application, generate a new online profile with the correct present address mapping, and book a new appointment at the legitimate RPO. Fix Timeline: 1 to 2 working days to generate a new offline A-Challan and secure a new portal slot. Fix Cost: A catastrophic financial penalty; because passport fees are strictly non-refundable regardless of circumstance, the citizen loses the initial payment entirely (minimum TK 4,025) and must pay the full fee again. Salvageability: The misrouted application is zero percent salvageable.",
"key_terms_bengali": [
"বর্তমান ঠিকানা",
"আঞ্চলিক পাসপোর্ট অফিস",
"অধিক্ষেত্র (থানা)"
],
"key_terms_english": [
"Present Address",
"Jurisdictional Boundary",
"Regional Passport Office"
],
"confidence_level": "high",
"source_urls": [
"https://dip.gov.bd/pages/static-pages/6922e11b933eb65569e2a3de",
"https://dip.gov.bd/pages/static-pages/6922de9e933eb65569e1c12f"
],
"flags": []
},
{
"chunk_id": "epassport_7_missing_digital_noc",
"chunk_type": "rejection_analysis",
"section_header": "REJECTION REASONS & EXACT FIXES",
"intent_tags": [
"rejection_fix",
"document_checklist",
"system_dependencies"
],
"content": "Government servants face a highly specific rejection trigger: the Missing or Un-uploaded Digital NOC/GO. The Root Cause is a strict cybersecurity mandate requiring that any No Objection Certificate (NOC), Government Order (GO), or Post Retirement Leave (PRL) document granting express priority must be visibly hosted on the issuing ministry's official web portal. Detection Stage: This failure is detected at Counter 1 during primary enrollment screening. Exact Remedial Steps: The applicant cannot rely on physical signatures alone. They must aggressively coordinate with their parent ministry's IT administration to upload the scanned NOC PDF to the departmental website so the RPO desk officer can verify the URL live. [FLAG: PRACTICE_VS_POLICY] Officially, this digital redundancy prevents fraud; in practice, when a ministry's archaic website experiences downtime or administrative staff delay the upload, passport clerks rigidly reject the applicant, refusing to accept perfectly valid physical, wet-ink documents. Fix Timeline: 1 to 3 working days, entirely dependent on the responsiveness of the applicant's external HR/IT department. Fix Cost: No additional passport processing fees are incurred. Salvageability: The original application and payment are fully salvageable; the citizen simply returns to the RPO once the web-link is active.",
"key_terms_bengali": [
"সরকারি আদেশ (জিও)",
"অনাপত্তি সনদ (এনওসি)",
"অনলাইন যাচাই"
],
"key_terms_english": [
"Government Order (GO)",
"No Objection Certificate (NOC)",
"Digital Upload"
],
"confidence_level": "high",
"source_urls": [
"https://wellington.mofa.gov.bd/pages/static-pages/%E0%A6%87-%E0%A6%AA%E0%A6%BE%E0%A6%B8%E0%A6%AA%E0%A7%8B%E0%A6%B0%E0%A7%8D%E0%A6%9F%E0%A7%87%E0%A6%B0-%E0%A6%AA%E0%A6%A6%E0%A7%8D%E0%A6%A7%E0%A6%A4%E0%A6%BF-%E0%A6%8F%E0%A6%AC%E0%A6%82-%E0%A6%AA%E0%A7%8D%E0%A6%B0%E0%A6%AF%E0%A6%BC%E0%A7%8B%E0%A6%9C%E0%A6%A8%E0%A7%80%E0%A6%AF%E0%A6%BC%E0%A6%A4%E0%A6%BE-xy1toj-696d982b0ff82b716068256e",
"https://chennai.mofa.gov.bd/pages/static-pages/695266b135ce18e1c05aacfc"
],
"flags": [
"PRACTICE_VS_POLICY"
]
},
{
"chunk_id": "epassport_7_inconsistent_transliteration",
"chunk_type": "rejection_analysis",
"section_header": "REJECTION REASONS & EXACT FIXES",
"intent_tags": [
"rejection_fix",
"document_checklist",
"advisory"
],
"content": "A frequent bureaucratic roadblock is Inconsistent Transliteration or Spelling on secondary matching documents. The Root Cause arises when mandatory supplementary evidence—such as a registered Marriage Certificate (Nikahnama), Divorce Letter (Talaknama), or educational certificates (SSC/HSC)—displays English spelling variations compared to the primary NID. Detection Stage: This is flagged either during Counter 1 manual screening or later during manual backend administrative review. Exact Remedial Steps: The citizen has two pathways. They must either return to the issuing agency (e.g., the Kazi office or Education Board) to officially amend the secondary document's spelling, or they must procure a notarized 'One and Same Person' affidavit sworn before a 1st Class Magistrate to legally reconcile the disparate spellings. Fix Timeline: Procuring a magistrate affidavit or amending a Nikahnama typically delays the process by 15 to 30 working days. Fix Cost: The applicant incurs heavy external legal and notary fees (ranging from TK 1,500 to TK 5,000 depending on the lawyer), but no secondary passport fee is required if the file was just paused at the desk. Salvageability: The application is generally salvageable. Front-desk officers typically 'hold' the physical file for a few days, allowing the applicant to return with the corrected evidence without paying a new e-Challan.",
"key_terms_bengali": [
"নামের বানান ভুল",
"কাবিননামা",
"হলফনামা"
],
"key_terms_english": [
"Inconsistent Transliteration",
"Marriage Certificate",
"Magistrate Affidavit"
],
"confidence_level": "high",
"source_urls": [
"https://bhclondon.org.uk/e-passport-application",
"https://hongkong.mofa.gov.bd/pages/static-pages/6952669435ce18e1c05aa2c2"
],
"flags": []
}
]
