# 🎓 Certificate Credit Points Validation System

A LangGraph-powered React Agent that validates professional certificates from **Credly badges**, checks expiration status, and automatically calculates **credit points**.

---

## ✨ Features

* 🔍 **Credly Badge Parsing** – Automatically extracts certificate information from Credly badge URLs.
* ⏰ **Expiration Validation** – Checks if certificates are valid or expired.
* 💯 **Credit Point Calculation** – Matches certificates with a local database and assigns credit points.
* 🤖 **AI-Powered Agent** – Uses LangGraph React Agent for natural language understanding.
* 🚀 **Fast & Free** – Powered by Groq API for lightning-fast LLM inference.
* 📊 **Multi-Certificate Support** – Calculate total credits for multiple certifications.

---

## 🎯 Use Cases

* Educational institutions tracking student certifications.
* Companies managing employee professional development credits.
* Training programs validating completion certificates.
* HR departments tracking team certifications.

---

## 🛠️ Technology Stack

* **LangGraph** – Agent orchestration framework.
* **LangChain** – LLM application framework.
* **Groq API** – Fast, free LLM inference (Llama 3.1).
* **Selenium** – Web scraping for Credly badges.
* **Python 3.8+** – Core programming language.

---

## 📋 Prerequisites

* Python 3.8 or higher
* Chrome/Chromium browser (for Selenium)
* Groq API key (get it free at [console.groq.com](https://console.groq.com))

---

## 🚀 Installation

### 1️⃣ Clone the Repository

```bash
git clone https://github.com/yourusername/certificate-validation-system.git
cd certificate-validation-system
```

### 2️⃣ Install Dependencies

```bash
pip install langgraph langchain langchain-groq selenium webdriver-manager python-dateutil
```

### 3️⃣ Set Up Groq API Key

#### Windows (CMD):

```cmd
set GROQ_API_KEY=your-key-here
```

```cmd
set LANGSMITH_API_KEY=your-key-here
```




## 💻 Usage

### Run in Interactive Mode

```bash
python react_agent_hw.py
```

### Example Queries

```
👤 User: How many credit points can I get for https://www.credly.com/badges/e192db17-f8c5-46aa-8f99-8a565223f1d6
👤 User: If I clear AWS Solution Architect Professional, how many points will I get?
👤 User: List all certificates
👤 User: What is the credit value of Terraform certification?
👤 User: Calculate total credits for AWS Solutions Architect and Kubernetes CKA
```

### Sample Output

```
🤖 System: Badge Information:
- Name: HashiCorp Certified: Terraform Associate (002) Issued by HashiCorp
- Holder: Cladius Fernando
- Issued: January 09, 2021
- Expires: September 09, 2023
- Status: EXPIRED
```

---



## 🏗️ Project Structure

```
certificate-validation-system/
├── react_agent_hw.py          # Main agent implementation
├── certificate.json            # Certificate database
├── README.md                   # This file
├── requirements.txt            # Dependencies
└── certificate_hw.py           # Main agent implementation
```

---

## 🧩 Tools Available

### 1. parse_credly_badge_and_get_credits

Parses a Credly badge URL and determines credit points eligibility.

* **Args:** `url (str)` → Credly badge URL
* **Returns:** Badge info, expiration status, and credit points

### 2. list_all_certificates

Lists all available certificates with their credit points.

### 3. search_certificate_by_name

Searches for certificates by name.

* **Args:** `query (str)` → Certificate name or keywords

### 4. calculate_total_credits_for_certificates

Calculates total credit points for multiple certificates.

* **Args:** `certificate_names (List[str])`

---

## 🔍 How It Works

1. **User Query** → User asks about credit points for a certificate.
2. **Agent Reasoning** → LangGraph React Agent chooses the right tool.
3. **Web Scraping** → Selenium extracts badge data from Credly.
4. **Date Validation** → Checks if the certificate is expired.
5. **Database Matching** → Finds the closest certificate name in the database.
6. **Credit Calculation** → Returns credit points and status.

---

## 🎨 Supported Certificate Formats

The parser handles multiple date formats:

* `Issued Oct 2024 • Expires Oct 2027`
* `Issued Oct 21, 2024 • Expired Sept 09, 2023`
* `Date issued: January 09, 2021`
* `This badge does not expire`

---

