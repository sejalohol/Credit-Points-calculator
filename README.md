#🎓 Certificate Credit Points Validation System

A LangGraph-powered React Agent that validates professional certificates from Credly badges, checks expiration status, and calculates credit points automatically.

#✨ Features

🔍 Credly Badge Parsing - Automatically extracts certificate information from Credly badge URLs
⏰ Expiration Validation - Checks if certificates are still valid or have expired
💯 Credit Point Calculation - Matches certificates against a database and assigns credit points
🤖 AI-Powered Agent - Uses LangGraph React Agent with natural language understanding
🚀 Fast & Free - Powered by Groq API for lightning-fast LLM inference
📊 Multi-Certificate Support - Calculate total credits for multiple certifications

#🎯 Use Cases

Educational institutions tracking student certifications
Companies managing employee professional development credits
Training programs validating completion certificates
HR departments tracking team certifications

#🛠️ Technology Stack

LangGraph - Agent orchestration framework
LangChain - LLM application framework
Groq API - Fast, free LLM inference (Llama 3.1)
Selenium - Web scraping for Credly badges
Python 3.8+ - Core programming language

#📋 Prerequisites

Python 3.8 or higher
Chrome/Chromium browser (for Selenium)
Groq API key (free at console.groq.com)

#🚀 Installation
1. Clone the Repository
bashgit clone https://github.com/yourusername/certificate-validation-system.git
cd certificate-validation-system
3. Install Dependencies
bashpip install langgraph langchain langchain-groq selenium webdriver-manager python-dateutil
4. Set Up Groq API Key
Get your free API key from Groq Console
Windows (CMD):
cmdset GROQ_API_KEY=your-key-here
Windows (PowerShell):
powershell$env:GROQ_API_KEY='your-key-here'
Linux/Mac:
bashexport GROQ_API_KEY='your-key-here'
5. Prepare Certificate Database
Create a certificate.json file in the project directory:
json[
  {
    "certificate_name": "HashiCorp Certified: Terraform Associate",
    "credit_points": 5.0
  },
  {
    "certificate_name": "AWS Certified Solutions Architect - Professional",
    "credit_points": 10.0
  },
  {
    "certificate_name": "Certified Kubernetes Administrator (CKA)",
    "credit_points": 7.0
  }
]
💻 Usage
Interactive Mode
bashpython react_agent_hw.py
Example Queries
👤 User: How many credit points can I get for https://www.credly.com/badges/e192db17-f8c5-46aa-8f99-8a565223f1d6

👤 User: If I clear AWS Solution Architect Professional how many points will I get?

👤 User: List all certificates

👤 User: What is the credit value of Terraform certification?

👤 User: Calculate total credits for AWS Solutions Architect and Kubernetes CKA
Sample Output
🤖 System: Badge Information:
- Name: HashiCorp Certified: Terraform Associate (002) Issued by HashiCorp
- Holder: Cladius Fernando
- Issued: January 09, 2021
- Expires: September 09, 2023
- Status: EXPIRED


🔧 LangGraph Server Deployment
The agent can be deployed as a LangGraph server:
bashlanggraph up
The graph object is exported at module level for LangGraph compatibility.
🏗️ Project Structure
certificate-validation-system/
├── react_agent_hw.py          # Main agent implementation
├── certificate.json            # Certificate database
├── README.md                   # This file
└── requirements.txt            # Python dependencies (optional)
🛠️ Tools Available
The agent has access to these tools:
1. parse_credly_badge_and_get_credits
Parses a Credly badge URL and determines credit points eligibility.
Args:

url (str): Credly badge URL

Returns:

Badge information, expiration status, and credit points

2. list_all_certificates
Lists all available certificates with their credit points.
3. search_certificate_by_name
Searches for certificates by name and returns credit information.
Args:

query (str): Certificate name or keywords

4. calculate_total_credits_for_certificates
Calculates total credit points for multiple certificates.
Args:

certificate_names (List[str]): List of certificate names

🔍 How It Works

User Query - User asks about credit points for a certificate
Agent Reasoning - LangGraph React Agent decides which tool to use
Web Scraping - Selenium extracts badge information from Credly
Date Validation - Checks if certificate is expired
Database Matching - Fuzzy matches certificate name against database
Credit Calculation - Returns credit points if valid

🎨 Supported Certificate Formats
The parser handles various Credly date formats:

"Issued Oct 2024 • Expires Oct 2027"
"Issued Oct 21, 2024 • Expired Sept 09, 2023"
"Date issued: January 09, 2021"
"This badge does not expire"

