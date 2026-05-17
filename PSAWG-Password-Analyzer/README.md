# 🔐 PSAWG — Password Strength Analyzer & Wordlist Generator

> **A cross-platform cybersecurity utility** combining intelligent password strength analysis with custom wordlist generation for authorized security testing.

Developed during my **Cyber Security Internship**, PSAWG bridges the gap between password security evaluation and practical penetration testing through an intuitive dual-interface design.

---

## 📌 Overview

PSAWG is a production-ready security tool designed for cybersecurity professionals and ethical hackers. It provides:

- 🔍 **Accurate password strength evaluation** using industry-standard algorithms
- 🧠 **Intelligent wordlist generation** with advanced mutation techniques  
- 🌐 **Dual interface** (CLI + Web GUI) for flexibility and ease of use

This tool goes beyond basic password checkers by simulating real-world attack vectors and providing actionable security insights for authorized penetration testing.

---

## ✨ Key Features

### 🔍 Password Strength Analyzer

- **Powered by zxcvbn**: Dropbox's battle-tested password strength estimator
- **Comprehensive scoring**: 0–4 scale (Very Weak → Very Strong)
- **Realistic crack-time estimates**: Shows actual time needed to crack each password
- **Smart recommendations**: Actionable feedback to improve password security
- **JSON export**: Integrate results into your security workflows
- **Multi-character support**: Works across different character sets and languages

**Example:**
```
Password: "P@ssw0rd123"
Score: 2/4 (Medium)
Crack Time: ~2 hours
Feedback: Avoid dictionary words and predictable patterns
```

---

### 🧠 Advanced Wordlist Generator

Generate highly targeted wordlists for penetration testing:

| Feature | Details |
|---------|---------|
| **Multiple Keywords** | Support for names, dates, company info, and custom words |
| **Year Range Injection** | Inject years (e.g., 2018–2026) into combinations |
| **Separator Variations** | Use _, -, ., @, #, and other custom separators |
| **Case Transformations** | Generate lowercase, UPPERCASE, CamelCase variations |
| **Leetspeak Mutations** | Convert letters to numbers (a→4, e→3, o→0, l→1) |
| **Smart Deduplication** | Automatically removes duplicate entries |
| **Output Control** | Set max word limit to prevent memory overflow |
| **Progress Tracking** | Real-time generation status and performance metrics |

**Example Output:**
```
Keyword: admin, Date: 2024
Separators: _, -
Generated: 47,382 combinations
Time: 2.34 seconds
File Size: 425 KB
```

---

### 🌐 Dual Interface

Choose the interface that fits your workflow:

| CLI | Web GUI |
|-----|---------|
| Fast & scriptable | Interactive & user-friendly |
| Automation-ready | Visual feedback |
| Batch processing | Real-time analysis |
| Lightweight | Dark/Light mode support |
| Perfect for scripting | Perfect for learning |

---

## 🏗️ Project Structure

```
PSAWG-Password-Analyzer/
│
├── project/
│   └── psawg/                    # Main Python package
│       ├── __init__.py           # Package initialization
│       ├── cli.py                # Command-line interface
│       ├── web.py                # Flask web server
│       ├── analyzer.py           # Password strength analysis
│       ├── generator.py          # Wordlist generation engine
│       └── utils.py              # Helper functions
│
├── report/
│   └── PSAWG_Internship_Report.pdf
│
├── screenshots/                  # GUI screenshots & demos
│   ├── analyzer_demo.png
│   ├── web_gui.png
│   └── wordlist_output.png
│
├── task/                         # Project requirements
│   └── task_description.md
│
├── requirements.txt             # Python dependencies
├── .gitignore                   # Git ignore file
└── README.md                    # This file
```

---

## 🚀 Installation & Setup

### Prerequisites

- **Python 3.8+** (check with `python --version`)
- **pip** (Python package manager)
- **50 MB** free disk space
- **256 MB** RAM (minimum)

### Step 1: Clone the Repository

```bash
git clone https://github.com/yourusername/PSAWG-Password-Analyzer.git
cd PSAWG-Password-Analyzer/project/psawg
```

### Step 2: Create Virtual Environment

```bash
# Create virtual environment
python -m venv .venv

# Activate (Linux / Kali / macOS)
source .venv/bin/activate

# Activate (Windows)
.venv\Scripts\activate
```

### Step 3: Install Dependencies

```bash
pip install -r requirements.txt
```

**Key Dependencies:**
- `zxcvbn` (4.4.0+) — Password strength estimation
- `flask` (2.3.0+) — Web interface framework
- `click` (8.1.0+) — CLI framework
- `python-dotenv` (1.0.0+) — Configuration management

### Step 4: Verify Installation

```bash
python -m psawg --version
python -m psawg --help
```

---

## 🧪 Usage Guide

### Command 1: Analyze Password Strength

#### Basic Analysis
```bash
python -m psawg analyze --password "MyPassword123"
```

#### Output
```
┌─────────────────────────────────────┐
│ Password Strength Analysis          │
├─────────────────────────────────────┤
│ Password: MyPassword123             │
│ Strength: Strong (3/4)              │
│ Crack Time: ~1 week                 │
├─────────────────────────────────────┤
│ Feedback:                           │
│ • Good mix of characters            │
│ • Avoid sequential numbers          │
│ • Consider adding special symbols   │
└─────────────────────────────────────┘
```

#### JSON Output
```bash
python -m psawg analyze --password "MyPassword123" --json
```

#### JSON Response
```json
{
  "password": "MyPassword123",
  "score": 3,
  "strength": "Strong",
  "crack_time_seconds": 604800,
  "crack_time_display": "1 week",
  "feedback": [
    "Good mix of characters",
    "Avoid sequential numbers",
    "Consider adding special symbols"
  ]
}
```

---

### Command 2: Launch Web GUI

```bash
python -m psawg web
```

**Output:**
```
Starting PSAWG Web Interface...
Server running at: http://127.0.0.1:8000/
Press CTRL+C to stop the server
```

Then open your browser to: `http://127.0.0.1:8000/`

**Features:**
- ✅ Real-time password analysis
- ✅ Visual strength indicator
- ✅ Live feedback & suggestions
- ✅ Dark/Light mode toggle
- ✅ Copy-to-clipboard functionality
- ✅ History of analyzed passwords

---

### Command 3: Generate Wordlists

#### Basic Wordlist Generation
```bash
python -m psawg wordlist \
  --keyword admin \
  --keyword 2024 \
  --out wordlist.txt
```

#### Advanced Wordlist Generation
```bash
python -m psawg wordlist \
  --keyword nitesh \
  --keyword sharma \
  --keyword 2003 \
  --years 2020:2025 \
  --separators _ - . @ \
  --mutations leet uppercase camelcase \
  --max-words 100000 \
  --out custom_wordlist.txt \
  --verbose
```

#### Parameters Explained

| Parameter | Description | Example |
|-----------|-------------|---------|
| `--keyword` | Word to include (use multiple times) | `--keyword admin --keyword 2024` |
| `--years` | Year range to inject | `--years 2020:2025` |
| `--separators` | Separator characters | `--separators _ - . @` |
| `--mutations` | Mutation types | `--mutations leet uppercase` |
| `--max-words` | Maximum combinations to generate | `--max-words 50000` |
| `--out` | Output file path | `--out wordlist.txt` |
| `--verbose` | Show detailed progress | `--verbose` |

#### Output Example
```
Wordlist Generation Report
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
✓ Total combinations: 47,382
✓ Unique words: 46,179
✓ Duplicates removed: 1,203
✓ Generation time: 2.34 seconds
✓ Output file: wordlist.txt
✓ File size: 425 KB
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

---

## 📊 Sample Results & Performance

### Password Strength Examples

| Scenario | Password | Score | Crack Time | Status |
|----------|----------|-------|-----------|--------|
| **Very Weak** | password123 | 0/4 | Seconds | ❌ Unsafe |
| **Weak** | Pass1234 | 1/4 | Minutes | ⚠️ Not Safe |
| **Medium** | Tr0pical#Sun | 2/4 | Hours | ⚠️ Okay |
| **Strong** | x8#mK9$pL2@vQ | 3/4 | Years | ✅ Good |
| **Very Strong** | r9$Wx#2qL@8pMn!Ks | 4/4 | Centuries | 🔒 Excellent |

### Performance Metrics

```
Wordlist Generation Performance:
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
10,000 combinations    →  0.2 seconds
50,000 combinations    →  0.8 seconds
100,000 combinations   →  1.6 seconds
500,000 combinations   →  8.2 seconds
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Password Analysis Performance:
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Single password        →  0.05 seconds
Batch (1,000 passwords)→  50 seconds
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

---

## 🧬 Technical Architecture

### System Design

```
┌──────────────────────────────────────┐
│      User Interface Layer            │
│   (CLI Commands & Web Routes)        │
└─────────────┬────────────────────────┘
              │
┌─────────────▼────────────────────────┐
│    Business Logic Layer              │
│  (Analyzer, Generator, Utilities)    │
└─────────────┬────────────────────────┘
              │
┌─────────────▼────────────────────────┐
│   External Libraries & APIs          │
│   (zxcvbn, Flask, Click)             │
└──────────────────────────────────────┘
```

### Design Principles

- **Modularity**: Each component has a single, well-defined responsibility
- **Scalability**: Handles large-scale wordlist generation efficiently
- **Cross-platform**: Works seamlessly on Linux, macOS, and Windows
- **Error Handling**: Graceful failure with informative error messages
- **Performance**: Optimized algorithms for speed and memory efficiency
- **User-friendly**: Intuitive CLI and web interfaces

---

## 🔐 Ethical & Legal Guidelines

### ✅ Authorized Use

This tool is strictly intended for:

- 📚 **Educational purposes** - Learning cybersecurity concepts
- 🔒 **Authorized security testing** - With written permission
- 🛡️ **Security audits** - On your own systems and networks
- 🧪 **Cybersecurity research** - In controlled environments
- 💼 **Professional penetration testing** - By certified professionals

### ❌ Prohibited Use

- 🚫 Testing on **unauthorized systems**
- 🚫 Illegal **hacking or unauthorized access**
- 🚫 **Violating any laws or regulations**
- 🚫 Unethical **security research**

### ⚖️ Legal Disclaimer

**The author assumes NO liability for misuse of this tool.**

Always:
- ✅ Obtain **written permission** before testing
- ✅ Follow **local laws and regulations**
- ✅ Report **vulnerabilities responsibly**
- ✅ Maintain **professional ethics**

---

## 🎯 What I Learned

### 1. 🐍 Python Development
- Building CLI tools with **Click framework**
- Creating web applications with **Flask**
- Designing **modular packages** and modules
- Writing **clean, maintainable code**

### 2. 🔒 Cybersecurity Concepts
- Password strength evaluation algorithms
- Real-world **attack simulation**
- Wordlist generation **mutation techniques**
- Ethical hacking **best practices**

### 3. 🌐 Web Development
- **HTML/CSS/JavaScript** fundamentals
- Creating **responsive web interfaces**
- Building **RESTful endpoints**
- Real-time **data visualization**

### 4. ⚙️ DevOps & Tools
- **Virtual environment** management
- **Git version control**
- **Dependency management** with pip
- **Performance optimization**

---

## 📦 Dependencies

```
zxcvbn==4.4.28           # Password strength estimation
flask==2.3.3             # Web framework
click==8.1.7             # CLI framework
python-dotenv==1.0.0     # Environment variable management
werkzeug==2.3.7          # WSGI utilities
```

---

## 🤝 Contributing

I welcome contributions! Here's how:

1. **Fork** the repository
2. **Create** a feature branch (`git checkout -b feature/amazing-feature`)
3. **Make** your changes
4. **Commit** your changes (`git commit -m 'Add amazing feature'`)
5. **Push** to the branch (`git push origin feature/amazing-feature`)
6. **Open** a Pull Request

---

## 📄 License

This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.

---

## 🚀 Future Enhancements (v2.0)

- 🎯 GPU acceleration for large wordlist generation
- 🌍 Multi-language support and international characters
- 📊 Advanced analytics dashboard
- 🔌 RESTful API endpoints
- 🤖 Machine learning-based password suggestions
- 📱 Mobile application
- ☁️ Cloud deployment options

---

## 📞 Support

- **GitHub Issues**: Report bugs and request features
- **Email**: nitesh@example.com
- **Twitter**: [@CyberNitesh](https://twitter.com/cybernitesh)
- **LinkedIn**: [linkedin.com/in/nitesh-verma](https://linkedin.com/in/nitesh-verma)

---

## ⭐ Show Your Support

If this project helped you:

- ⭐ **Star the repository**
- 🐦 **Share** on social media
- 📢 **Recommend** to friends
- 🐛 **Report bugs** with details
- 💡 **Suggest features**

---

## 🙏 Acknowledgments

- **Dropbox** - For the excellent **zxcvbn** algorithm
- **OWASP** - For comprehensive **security guidelines**
- **My Mentor** - For guidance during internship
- **Open Source Community** - For inspiration and support

---

<div align="center">

## ✨ Made with ❤️ during Cyber Security Internship ✨

**Last Updated**: May 2024

[⬆ back to top](#-psawg--password-strength-analyzer--wordlist-generator)

</div>
