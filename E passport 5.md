[
{
"chunk_id": "epassport_5_domestic_bdt_fees",
"chunk_type": "fee_structure",
"section_header": "FEES (COMPLETE)",
"intent_tags": [
"cost_query",
"procedural_step",
"faq"
],
"content": "The domestic financial structure for the Bangladesh e-Passport incorporates a 15% Government Value Added Tax (VAT) natively embedded within the final cost. The precise fee matrix in Bangladeshi Taka (BDT) is legally regimented by booklet size, validity, and delivery tier. For 48-page booklets: a 5-year validity costs TK 4,025 (Regular - 15 to 21 working days), TK 6,325 (Express - 7 to 10 working days), and TK 8,625 (Super Express - 2 working days) [FLAG: VERIFY_2026]. For a 10-year validity, it escalates to TK 5,750 (Regular), TK 8,050 (Express), and TK 10,350 (Super Express) [FLAG: VERIFY_2026]. For 64-page booklets catering to frequent travelers: a 5-year validity is priced at TK 6,325 (Regular), TK 8,625 (Express), and TK 12,075 (Super Express) [FLAG: VERIFY_2026]. The premium 64-page, 10-year validity tier costs TK 8,050 (Regular), TK 10,350 (Express), and TK 13,800 (Super Express) [FLAG: VERIFY_2026]. Notably, government employees presenting a digital No Objection Certificate (NOC) or Post Retirement Leave (PRL) document are legally entitled to receive Express processing while only paying the Regular fee tier, or Super Express delivery while paying the Express fee tier.",
"key_terms_bengali": [
"ই-পাসপোর্ট ফি",
"মূল্য সংযোজন কর (ভ্যাট)",
"সরকারি চাকরিজীবী"
],
"key_terms_english": [
"Base Fee",
"Value Added Tax (VAT)",
"Government Surcharge"
],
"confidence_level": "high",
"source_urls": [
"https://tipsoi.pro/biometric-e-passport-bangladesh/",
"https://www.epassport.gov.bd/instructions/passport-fees"
],
"flags": [
"VERIFY_2026"
]
},
{
"chunk_id": "epassport_5_overseas_surcharges",
"chunk_type": "fee_structure",
"section_header": "FEES (COMPLETE)",
"intent_tags": [
"cost_query",
"advisory",
"procedural_step"
],
"content": "For the diaspora applying through overseas foreign missions, the fee structure shifts to foreign currency (primarily USD, EUR, or local equivalents like AED and CAD) and introduces mandatory institutional surcharges. Beyond the base processing fee, expatriate applicants are legally required to pay an absolute 10% surcharge that is explicitly routed to the Wage Earners' Welfare Fund. For example, a standard 48-page, 5-year regular e-Passport has a base fee of USD 100 for general applicants, culminating in a total of USD 110 after the surcharge is applied [FLAG: VERIFY_2026]. Foreign missions strictly prohibit cash or personal checks, mandating official cashier's checks or bank drafts to mitigate financial fraud. Additionally, the state provides massive subsidies for overseas students and laborers. A 48-page, 5-year regular passport costs merely USD 30 (base) for verified students, generating a highly reduced total of USD 33 [FLAG: VERIFY_2026].",
"key_terms_bengali": [
"ওয়েজ আর্নার্স কল্যাণ তহবিল",
"সারচার্জ",
"প্রবাসী ফি"
],
"key_terms_english": [
"Wage Earners Welfare Fund",
"Surcharge",
"Foreign Mission"
],
"confidence_level": "high",
"source_urls": [
"https://abudhabi.mofa.gov.bd/pages/static-pages/6952667d35ce18e1c05a9876",
"https://losangeles.mofa.gov.bd/pages/static-pages/695266a835ce18e1c05aa9eb"
],
"flags": [
"VERIFY_2026"
]
},
{
"chunk_id": "epassport_5_payment_gateways_friction",
"chunk_type": "procedural_guide",
"section_header": "FEES (COMPLETE)",
"intent_tags": [
"cost_query",
"system_dependencies",
"fraud_warning"
],
"content": "The Department of Immigration and Passports (DIP) authorizes two primary financial avenues for fee collection. Online payments are funneled through state-sanctioned payment gateways: EkPay, DGePay, and ShurjoPay, which accept major credit cards and mobile financial services like bKash, Nagad, Rocket, and Upay. Offline payments must be executed via the Automated Challan System (A-Challan), which generates a physical e-Challan barcode. Citizens can deposit offline fees at an extensive network of government and commercial banks, explicitly including Sonali Bank, Agrani Bank, AB Bank, Mutual Trust Bank (MTB), Bangladesh Commerce Bank Limited (BCBL), and Citizens Bank PLC. [FLAG: PRACTICE_VS_POLICY] Despite the heavy promotion of digital payments, massive systemic friction exists within the online gateways. Ground-truth reports reveal that the API frequently crashes during high-traffic hours; mobile wallets routinely deduct the exact passport fee from the citizen's financial balance, but the portal crashes before generating the mandatory digital PDF receipt. This systemic failure forces applicants into a grueling 24 to 48-hour wait for API reconciliation or drives them to pay the fee a second time offline at a physical bank just to secure a receipt for their biometric appointment.",
"key_terms_bengali": [
"এ-চালান",
"পেমেন্ট গেটওয়ে",
"ব্যাংক ড্রাফট"
],
"key_terms_english": [
"A-Challan",
"Automated Challan System",
"Payment Gateway"
],
"confidence_level": "high",
"source_urls": [
"https://www.researchgate.net/publication/367336483_Usability_Analysis_of_Bangladesh_e-Passport_Portal_A_Study_on_Public_Software_Project",
"https://www.epassport.gov.bd/instructions/passport-fees"
],
"flags": [
"PRACTICE_VS_POLICY"
]
},
{
"chunk_id": "epassport_5_penalties_corrections",
"chunk_type": "fee_structure",
"section_header": "FEES (COMPLETE)",
"intent_tags": [
"cost_query",
"rejection_fix",
"advisory"
],
"content": "The e-Passport financial framework enforces a rigid, zero-refund policy across all application types. Statutory guidelines explicitly dictate that passport fees are non-refundable under all circumstances, irrespective of application abandonment, backend biometric rejection, or voluntary withdrawal. Furthermore, there is no fractional or discounted administrative fee for executing a 'Samsodhoni' (data correction) or replacing a lost or stolen passport. Citizens forced to amend their demographic data or replace a lost booklet must pay the absolute full original fee of a brand new passport issuance, categorized strictly by their selected booklet size and delivery tier. Financial fraud or payment invalidation triggers immediate systemic penalties. If an offline money order, cashier's check, or bank draft is returned unpaid by the issuing bank due to insufficient funds, the DIP legally aborts the application, permanently freezes the passport profile, and reports the applicant to the Ministry of Home Affairs for attempting to defraud the state treasury.",
"key_terms_bengali": [
"জরিমানা",
"অফেরতযোগ্য",
"তথ্য সংশোধন"
],
"key_terms_english": [
"Non-Refundable",
"Samsodhoni",
"Lost Passport Penalty"
],
"confidence_level": "high",
"source_urls": [
"https://losangeles.mofa.gov.bd/pages/static-pages/695266a835ce18e1c05aa9eb",
"https://chennai.mofa.gov.bd/pages/static-pages/695266b135ce18e1c05aacfc"
],
"flags": []
}
]
