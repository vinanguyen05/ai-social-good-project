# ai-social-good-project
Addressing Food Insecurity
## Problem:
Low-income working families in high-cost areas such as San Jose and Santa Clara struggle to consistently access nutritious food, even when employed. Rising living costs and unstable income make it difficult for residents to locate reliable food assistance quickly. The project centers on people like Vina, a 20-year-old supporting her family while searching for accessible and updated food resources. The major breakdown is information accessibility. Food banks, SNAP resources, and meal assistance programs are spread across multiple websites, many of which are outdated or difficult to navigate. Users often waste time checking inaccurate hours, unclear eligibility requirements, or unavailable resources when they urgently need help.
## AI Capability:
The project uses natural language processing (NLP) and structured data extraction to address this failure point. NLP allows the system to understand user requests written conversationally, while structured extraction converts those requests into consistent fields such as location, urgency, and assistance type. This capability fits because food assistance requests vary widely in wording, language, and detail. Instead of requiring users to search manually, the AI interprets their needs, filters relevant programs, and generates understandable responses. The structured extraction component also makes the information usable for backend databases and automated recommendation systems.
## Workflow:
Input: Users provide information such as location, household size, income level, preferred language, and food needs through a web or mobile interface.
AI Processing: The AI analyzes the request using NLP, extracts structured information, and cross-references food assistance databases. It filters programs based on eligibility, location, urgency, and availability while prioritizing updated information.
Output: The system returns a curated list of nearby food resources, including addresses, eligibility requirements, contact details, and operating hours. Users can then choose which resource to contact or visit.
Structured extraction example:
<img width="1919" height="875" alt="image" src="https://github.com/user-attachments/assets/0dbe1719-7415-45fd-97dd-15142667758f" />
Edge case output:
<img width="964" height="59" alt="image" src="https://github.com/user-attachments/assets/3aa0610b-8ef5-47f9-ad12-f0d5df6c2712" />
## Failure Case: 
The system should have extracted language, urgency, and eligibility concerns. Instead, it only returned location and a generic food type. This matters because non-English users may receive incomplete or misleading recommendations, limiting their ability to access timely food assistance. 
One identified failure case involved a Spanish-language request:
“Necesito ayuda alimentaria en San Jose.”
The system partially succeeded by identifying the location (“San Jose”) and recognizing food-related terms. However, the output only returned:
{'location': 'San Jose', 'food_type': 'any food'}
This demonstrated that the English-centric parser could not fully capture the user’s intent or urgency. The lab output showed the possibility of incomplete multilingual understanding, meaning users who do not primarily speak English could receive weak or inaccurate recommendations.
## Oversight and Tradeoff: 
Human oversight is necessary when reviewing extracted information, validating updated program data, and handling ambiguous or multilingual requests. Staff members or community organizations would verify flagged results and ensure recommendations remain accurate and culturally appropriate.
Improving multilingual support would significantly increase accessibility, but it comes with tradeoffs. Expanding language coverage requires more advanced AI models, larger datasets, and continuous monitoring, increasing development costs and system complexity. While automation improves speed and scalability, maintaining accuracy still depends on periodic human review.
One improvement would be adding a multilingual translation or multilingual parsing layer before structured extraction. This would improve access for Spanish-speaking users, but it would increase cost, latency, and the need for human review.
