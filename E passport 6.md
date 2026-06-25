[
{
"chunk_id": "epassport_6_online_registration",
"chunk_type": "procedural_guide",
"section_header": "STEP-BY-STEP PROCESS (GROUND TRUTH EDITION)",
"intent_tags": [
"procedural_step",
"advisory",
"rejection_fix"
],
"content": "Embarking on your e-Passport journey begins at the official portal (epassport.gov.bd). Officially, you are expected to create an account, fill out demographic data perfectly matching your NID, and submit the online form. [FLAG: VERIFY_2026 - monitor the newly deployed 2026 UI updates which attempt to streamline calendar booking and automated form validation]. Ground Truth: The portal can be notoriously unstable during peak hours. A critical, frustrating failure point is the 'One-word name' or dot (.) problem; citizens with single names or initials face hard validation errors because the system algorithm rigidly demands both a first and last name. Furthermore, if you discover a data error after submitting the form, there is no simple 'cancel' button on the dashboard. [FLAG: PRACTICE_VS_POLICY] The official workaround requires completely abandoning the application and starting over. However, if you already paid the fee online, that money is permanently forfeited by the system, forcing you to pay double just to fix a simple typo.",
"key_terms_bengali": [
"অনলাইন আবেদন",
"ভুল তথ্য",
"বাতিল"
],
"key_terms_english": [
"Online Registration",
"One-word Name",
"Cancel Application"
],
"confidence_level": "high",
"source_urls": [
"https://recombd.com/applying-for-an-e-passport-in-bangladesh-2025-a-step-by-step-guide/"
],
"flags": [
"VERIFY_2026",
"PRACTICE_VS_POLICY"
]
},
{
"chunk_id": "epassport_6_payment_processing",
"chunk_type": "procedural_guide",
"section_header": "STEP-BY-STEP PROCESS (GROUND TRUTH EDITION)",
"intent_tags": [
"procedural_step",
"cost_query",
"fraud_warning"
],
"content": "After successfully submitting your form, the next crucial step is securing your application by paying the non-refundable fee. Official Expectation: You can seamlessly pay online via EkPay, bKash, Nagad, or credit cards, or opt to pay offline via A-Challan at designated commercial banks like Sonali or Bank Asia. Ground Truth: The online payment gateway is a massive systemic failure point that causes immense anxiety. During high-traffic windows, the API frequently crashes; mobile wallets will deduct the exact passport fee from your account, but the portal crashes before generating the mandatory digital PDF e-Challan receipt. Workaround: Veteran applicants and digital centers strictly advise against online payments to avoid this trap. The safest, most reliable street-level workaround is to generate an offline A-Challan barcode and physically deposit the cash at a bank branch. This guarantees you walk away with an immediate, physical, bank-stamped receipt necessary for your appointment. [FLAG: NEEDS_SOURCE - verify if the Ministry of Finance has implemented an automatic 24-hour refund API for failed EkPay transactions].",
"key_terms_bengali": [
"এ-চালান",
"পেমেন্ট গেটওয়ে",
"ব্যাংক রসিদ"
],
"key_terms_english": [
"A-Challan",
"Payment Gateway",
"Bank Receipt"
],
"confidence_level": "high",
"source_urls": [
"https://www.epassport.gov.bd/instructions/passport-fees",
"https://www.researchgate.net/publication/367336483_Usability_Analysis_of_Bangladesh_e-Passport_Portal_A_Study_on_Public_Software_Project"
],
"flags": [
"NEEDS_SOURCE"
]
},
{
"chunk_id": "epassport_6_biometric_enrollment",
"chunk_type": "procedural_guide",
"section_header": "STEP-BY-STEP PROCESS (GROUND TRUTH EDITION)",
"intent_tags": [
"procedural_step",
"document_checklist",
"advisory"
],
"content": "With your payment secured, it is time for the physical appointment at your Regional Passport Office (RPO). Official Expectation: You arrive peacefully at your scheduled online time slot, present your printed application summary, appointment slip, and original NID, and smoothly proceed to the biometric booth for 10-fingerprint capture, iris scanning, and a live photograph. Ground Truth: The scheduling calendar frequently freezes during booking, and actual 'appointment times' are largely ignored by RPO security due to sheer volume. [FLAG: PRACTICE_VS_POLICY] Although official instructions explicitly state no additional attested documents are required, front-desk clerks arbitrarily reject applicants for minor demographic mismatches, which account for a massive 70% of initial rejections. Workaround: Dress smartly in dark colors (avoiding white or light gray clothing that blends into the photo booth background) and arrive by 6:00 AM to secure a physical queue position, regardless of your printed time slot. Do not wear contact lenses or heavy glasses. Once successful, you will receive a printed delivery slip—guard this document with your life.",
"key_terms_bengali": [
"বায়োমেট্রিক তথ্য",
"আঙ্গুলের ছাপ",
"ডেলিভারি স্লিপ"
],
"key_terms_english": [
"Biometric Enrollment",
"Fingerprints",
"Delivery Slip"
],
"confidence_level": "high",
"source_urls": [
"https://chennai.mofa.gov.bd/pages/static-pages/695266b135ce18e1c05aacfc",
"https://tipsoi.pro/biometric-e-passport-bangladesh/"
],
"flags": [
"PRACTICE_VS_POLICY"
]
},
{
"chunk_id": "epassport_6_backend_verification",
"chunk_type": "system_dependencies",
"section_header": "STEP-BY-STEP PROCESS (GROUND TRUTH EDITION)",
"intent_tags": [
"timeline_query",
"system_dependencies",
"rejection_fix"
],
"content": "Once your biometrics are captured, your physical job is done, and your file enters the digital backend. Official Expectation: Under the groundbreaking February 2025 directives, manual police verification is abolished for standard applications; approval now relies purely on lightning-fast automated NID and BDRIS API verification. Ground Truth: Despite the policy shift, applications routinely stall in the dreaded 'Pending Backend Verification' phase. Common failure points include the AFIS (Automated Fingerprint Identification System) triggering a 'duplicate match' if you previously held an undisclosed MRP with altered data, or temporary API handshake failures between the passport server and the Election Commission's database. Workaround: There is no citizen-facing button to resolve backend holds. If your status remains stuck for weeks, you are often forced to physically visit the RPO and request an audience with the Assistant Director (often in Room 301) to manually push the file through the local server queue, a friction point where many unfortunately fall prey to brokers offering to 'clear the file'.",
"key_terms_bengali": [
"পুলিশ ভেরিফিকেশন",
"তথ্য যাচাই",
"সার্ভার"
],
"key_terms_english": [
"Backend Verification",
"Police Verification",
"AFIS Match"
],
"confidence_level": "high",
"source_urls": [
"https://en.prothomalo.com/bangladesh/r5ifkt4zs6",
"https://www.youtube.com/watch?v=8icOpTnvt4g"
],
"flags": []
},
{
"chunk_id": "epassport_6_physical_collection",
"chunk_type": "procedural_guide",
"section_header": "STEP-BY-STEP PROCESS (GROUND TRUTH EDITION)",
"intent_tags": [
"procedural_step",
"timeline_query",
"faq"
],
"content": "The final, rewarding phase is the physical retrieval of your brand new travel document. Official Expectation: The system generates an automated email and SMS notifying you exactly when the passport is ready, allowing you to walk in for collection between 11:00 AM - 12:30 PM and 2:00 PM - 4:30 PM. Ground Truth: The email notification frequently causes severe logistical confusion. An email stating 'Your passport is ready for issuance' technically means it has been successfully printed at the central facility in Dhaka, but it may take several more days to physically arrive via secure courier at your local regional field office. Common Failure Point: Eager citizens arrive immediately after receiving the email, only to be turned away at the gate because the physical booklet is still in transit. Workaround: Track your status manually on the portal and wait at least 48 hours after receiving the 'ready' notification before visiting your RPO. Collection absolutely requires surrendering your original delivery slip and allowing the counter clerk to permanently cancel (punch a hole in) your old MRP or previous e-Passport before handing over the new one.",
"key_terms_bengali": [
"পাসপোর্ট সংগ্রহ",
"ডেলিভারি স্লিপ",
"পুরাতন পাসপোর্ট বাতিল"
],
"key_terms_english": [
"Passport Collection",
"Email Notification",
"Passport Cancellation"
],
"confidence_level": "high",
"source_urls": [
"https://bhclondon.org.uk/e-passport-application",
"https://toronto.mofa.gov.bd/pages/static-pages/695266b435ce18e1c05aadf4"
],
"flags": []
}
]
