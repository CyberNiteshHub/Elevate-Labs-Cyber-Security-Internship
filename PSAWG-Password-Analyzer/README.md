# 🔐 PSAWG — Password Strength Analyzer & Wordlist Generator

A cross-platform cybersecurity utility built in Python that combines password strength analysis with a custom wordlist generator for real-world security testing.

Developed as part of my Cyber Security Internship, this project focuses on evaluating password security and generating targeted wordlists in a practical and efficient way.

---

## 📌 Overview

PSAWG is designed to assist in authorized security testing by providing:

- Accurate password strength evaluation  
- Intelligent wordlist generation  
- CLI + Web GUI interface  

It goes beyond basic tools by focusing on real-world attack simulation and usability.

---

## ⚙️ Key Features

### 🔍 Password Strength Analyzer
- Uses zxcvbn (Dropbox password strength estimator)  
- Score range (0–4): Very Weak → Very Strong  
- Realistic crack-time estimation  
- Actionable feedback & suggestions  
- JSON output support  

---

### 🧠 Wordlist Generator
- Generate targeted wordlists using custom keywords  
- Supports:
  - Multiple keywords (name, date, etc.)
  - Year range injection (2018–2026)
  - Separator variations (_, -, .)
  - Case transformations
  - Leetspeak mutations (a→4, e→3, etc.)
- Output file control with limit  

---

### 🌐 Dual Interface
- CLI (fast & scriptable)  
- Web GUI (interactive usage)  

---

## 🏗️ Project Structure


PSAWG-Password-Analyzer/
│
├── project/
│ └── psawg/
│
├── report/
│ └── PSAWG_Internship_Report.pdf
│
├── screenshots/
│
├── task/
│
└── wordlist.txt


---

## 🚀 Installation & Setup

### Clone Repository
```bash
git clone <your-repo-url>
cd PSAWG-Password-Analyzer/project/psawg
Create Virtual Environment
python -m venv .venv
Activate

Linux / Kali:

source .venv/bin/activate

Windows:

.venv\Scripts\activate
Install Dependencies
pip install -r requirements.txt
🧪 Usage
Analyze Password
python -m psawg analyze --password "P@ssw0rd123"
JSON Output
python -m psawg analyze --password "P@ssw0rd123" --json
Launch Web GUI
python -m psawg web

Open:

http://127.0.0.1:8000/
Generate Wordlist
python -m psawg wordlist \
--keyword nitesh \
--keyword 2003 \
--years 2018:2026 \
--separators _ - . \
--max-words 50000 \
--out wordlist.txt
📊 Sample Output
Weak passwords → cracked in seconds
Strong passwords → centuries to crack
Wordlists → 40,000+ combinations in under a second
🧠 Technical Highlights
Modular Python package design
CLI + Web integration
Real-world password evaluation logic
Efficient wordlist mutation engine
Cross-platform support
📸 Screenshots

All outputs, GUI, and working proof are available in the /screenshots folder.

⚠️ Ethical Disclaimer

This tool is strictly for:

Educational purposes
Authorized security testing

Do NOT use on unauthorized systems.

🎯 Learning Outcome
Password security concepts
Real-world attack simulation
Python CLI & Web development
Secure coding practices
👨‍💻 Author

Nitesh Verma (Cyber Nitesh)
Cyber Security Enthusiast | Ethical Hacker | Python Developer
