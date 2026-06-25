[
{
"chunk_id": "epassport_3_age_validity_brackets",
"chunk_type": "eligibility_requirements",
"section_header": "ELIGIBILITY & IDENTITY GATES",
"intent_tags": [
"eligibility_gate",
"procedural_step",
"faq"
],
"content": "The Bangladesh e-Passport system enforces strict age-based eligibility brackets that dictate the maximum booklet validity and specific digital identity prerequisites. Under the current statutory framework, adult citizens aged between 18 and 65 are exclusively eligible to receive a passport with a 10-year validity period. Conversely, the system algorithmically caps the validity at 5 years for all minors under 18 years of age and elderly citizens over 65 years of age. For identity verification, adults over 20 must present a National Identity (NID) card, while those between 18 and 20 may use either an NID or an online-verified 17-digit Birth Registration Certificate (BRC). All applicants aged 6 and above must physically appear at the passport office to provide full biometric data, including 10-fingerprint scans and dual iris recognition. Minors under the age of 6 are exempted from live biometric capture but must provide a lab-printed 3R-sized photograph with a white or gray background. [FLAG: VERIFY_2026 - monitor if the Department of Immigration and Passports alters the upper age limit for the 10-year validity tier in upcoming gazettes].",
"key_terms_bengali": [
"বয়স সীমা",
"মেয়াদ",
"বায়োমেট্রিক তথ্য"
],
"key_terms_english": [
"Age Brackets",
"Validity Period",
"Biometric Data"
],
"confidence_level": "high",
"source_urls": [
"https://en.wikipedia.org/wiki/Bangladeshi_passport",
"https://epassport.gov.bd/landing/notices/156"
],
"flags": [
"VERIFY_2026"
]
},
{
"chunk_id": "epassport_3_disqualifying_conditions",
"chunk_type": "security_advisory",
"section_header": "ELIGIBILITY & IDENTITY GATES",
"intent_tags": [
"security_advisory",
"fraud_warning",
"rejection_fix"
],
"content": "Clearing the e-Passport entry gate requires applicants to pass severe background and security thresholds. The primary statutory mechanism for disqualification stems from the Bangladesh Passport Order 1973, which legally empowers authorities to revoke or block a passport if an active court order bans the individual's departure or if the applicant is facing ongoing criminal litigation. During the biometric enrollment phase, the Automated Fingerprint Identification System (AFIS) performs a real-time deduplication sweep. If AFIS detects a duplicate biometric match linking the applicant to a previously undisclosed identity or an altered date of birth, the application triggers a hard systemic rejection. Additionally, state security agencies can intercept the issuance process. [FLAG: NEEDS_SOURCE - verify the specific operational parameters and database integration used to flag individuals for financial or banking loan defaults at the passport enrollment counter]. Citizens flagged for anti-state activities or major financial defaults face an administrative freeze, completely stalling their ability to procure a travel document until clearance is obtained from the Special Branch or the courts.",
"key_terms_bengali": [
"আদালতের নিষেধাজ্ঞা",
"ফৌজদারি মামলা",
"আঙ্গুলের ছাপ"
],
"key_terms_english": [
"Court Ban",
"Criminal Litigation",
"AFIS Match"
],
"confidence_level": "medium",
"source_urls": [
"https://immi.specialbranch.gov.bd/Passport_rules",
"https://www.irb-cisr.gc.ca/en/country-information/rir/Pages/index.aspx?doc=458512&pls=1"
],
"flags": [
"NEEDS_SOURCE"
]
},
{
"chunk_id": "epassport_3_identity_dependencies",
"chunk_type": "system_dependencies",
"section_header": "ELIGIBILITY & IDENTITY GATES",
"intent_tags": [
"system_dependencies",
"eligibility_gate",
"procedural_step"
],
"content": "The e-Passport architecture is structurally dependent on an absolute, real-time API handshake with two foundational civil registries: the Election Commission's NID database and the Office of the Registrar General's BDRIS birth certificate database. This linkage ensures that the Department of Immigration and Passports (DIP) functions solely as a printing authority, while the overarching identity verification is offloaded to the national databases. A systemic mismatch at the registration gate frequently occurs due to minor typographical discrepancies between the legacy passport and the NID, such as the abbreviation of 'Mohammed' to 'Md.' or slight variations in parental names. Furthermore, the BRC must natively contain all demographic data in English and be instantly verifiable via the everify.bdris.gov.bd portal. If the BRC data returns only in Bengali during the server query, the e-Passport software automatically blocks the application, forcing the citizen to physically amend their digital birth record before they can proceed. This strict synchronization prevents identity theft but creates a massive administrative bottleneck.",
"key_terms_bengali": [
"জাতীয় পরিচয়পত্র",
"জন্ম নিবন্ধন সনদ",
"তথ্য যাচাই"
],
"key_terms_english": [
"National Identity Card",
"Birth Registration Certificate",
"API Handshake"
],
"confidence_level": "high",
"source_urls": [
"https://bhclondon.org.uk/e-passport-application",
"https://chennai.mofa.gov.bd/pages/static-pages/695266b135ce18e1c05aacfc"
],
"flags": []
},
{
"chunk_id": "epassport_3_special_classes_minors_govt",
"chunk_type": "eligibility_requirements",
"section_header": "ELIGIBILITY & IDENTITY GATES",
"intent_tags": [
"document_checklist",
"procedural_step",
"rejection_fix"
],
"content": "Special applicant classes face highly specific evidentiary gates. For minors under 18, the core prerequisite is the 17-digit English-version BRC, but this must be supplemented by the physical presentation of both parents' original NID cards. [FLAG: PRACTICE_VS_POLICY] Although official policy demands parental NIDs, ground-truth reports indicate that when parents lack digitized NIDs (such as expatriate parents holding only foreign documents), field officers routinely reject the minor's application, ignoring alternative proofs of origin and forcing the family into bureaucratic limbo. For government servants and employees of autonomous bodies, the system bypasses standard police verification but demands a highly scrutinized No Objection Certificate (NOC) or Government Order (GO). To combat forged clearances, a strict 2025/2026 mandate requires that the NOC be visibly uploaded to the issuing ministry's official web portal. [FLAG: PRACTICE_VS_POLICY] In reality, if a ministry's website is down or the digital NOC is not uploaded in time, RPO front-desk clerks algorithmically reject the government employee, refusing to accept the physical paper copy.",
"key_terms_bengali": [
"অপ্রাপ্তবয়স্ক",
"অনাপত্তি সনদ",
"সরকারি আদেশ"
],
"key_terms_english": [
"Minors",
"No Objection Certificate",
"Government Order"
],
"confidence_level": "high",
"source_urls": [
"https://wellington.mofa.gov.bd/pages/static-pages/%E0%A6%87-%E0%A6%AA%E0%A6%BE%E0%A6%B8%E0%A6%AA%E0%A7%8B%E0%A6%B0%E0%A7%8D%E0%A6%9F%E0%A7%87%E0%A6%B0-%E0%A6%AA%E0%A6%A6%E0%A7%8D%E0%A6%A7%E0%A6%A4%E0%A6%BF-%E0%A6%8F%E0%A6%AC%E0%A6%82-%E0%A6%AA%E0%A7%8D%E0%A6%B0%E0%A6%AF%E0%A6%BC%E0%A7%8B%E0%A6%9C%E0%A6%A8%E0%A7%80%E0%A6%AF%E0%A6%BC%E0%A6%A4%E0%A6%BE-xy1toj-696d982b0ff82b716068256e"
],
"flags": [
"PRACTICE_VS_POLICY"
]
},
{
"chunk_id": "epassport_3_special_classes_nrb",
"chunk_type": "eligibility_requirements",
"section_header": "ELIGIBILITY & IDENTITY GATES",
"intent_tags": [
"eligibility_gate",
"advisory",
"document_checklist"
],
"content": "Non-Resident Bangladeshis (NRBs) face the most rigorous eligibility gates when applying through overseas diplomatic missions. Expatriates must provide a Bangladeshi NID or a 17-digit verified BRC. If an NRB has acquired foreign citizenship from one of the eligible nations, the state considers their Bangladeshi identity technically dormant. To override this, they must secure a Dual Nationality Certificate (DNC) from the Security Services Division, as a simple 'No Visa Required' (NVR) seal is legally insufficient to renew an e-Passport. A prevalent barrier for the diaspora is the 'Name Trap,' where foreign naturalization certificates reflect an anglicized or altered name compared to the Bangladeshi NID. This mismatch triggers an immediate rejection at the consular enrollment desk. NRBs are forced to reconcile this by executing a formal 'One and Same Person' affidavit. Furthermore, regardless of geographic distance from the embassy, biometric capture requires the applicant's mandatory physical presence; mail-in renewals are completely abolished under the e-Passport framework.",
"key_terms_bengali": [
"প্রবাসী বাংলাদেশী",
"দ্বৈত নাগরিকত্ব সনদ",
"হলফনামা"
],
"key_terms_english": [
"Non-Resident Bangladeshi",
"Dual Nationality Certificate",
"Name Trap"
],
"confidence_level": "high",
"source_urls": [
"https://legalseba.com/bd-articles/the-ultimate-guide-to-dual-citizenship-in-bangladesh/",
"https://toronto.mofa.gov.bd/pages/static-pages/695266b435ce18e1c05aadf4"
],
"flags": []
}
]
