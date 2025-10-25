# PrivCheck: Automated User Privilege Audit for Linux Systems

**PrivCheck** is a Python-based security automation tool designed to audit user privileges on Linux systems.  
It helps identify misconfigurations, excessive permissions, and inactive or default accounts that could lead to privilege escalation or insider threats.

---

## Features

- Enumerates all users and groups on the system
- Detects users with root or sudo access
- Flags accounts with no password or weak authentication
- Identifies inactive, orphaned, or default accounts
- Highlights users in sensitive groups (sudo, wheel, docker, etc.)
- Generates structured reports in **JSON** and **HTML** formats
- Provides suggested remediation steps for each finding

---

## Installation

1. Clone the repository:

```bash
git clone https://github.com/RodneyMcKnight/PrivCheck.git
cd PrivCheck

2. Create a vurtual envirnment and activate it:
python3 -m venv privcheck_venv
source privcheck_venv/bin/activate   # Windows: privcheck_venv\Scripts\activate

3. Install any dependencies (optional, for HTML templating):
pip install -r requirements.txt

Usage

Run PrivCheck with root privileges to audit all users:
sudo python3 privcheck.py --output report.json --html report.html

Example output:
{
  "user": "alice",
  "severity": "high",
  "title": "Member of sensitive group(s)",
  "details": "User is member of ['sudo']",
  "remediation": "Verify if this user requires sudo access; remove if unnecessary."
}

Security Disclaimer

Use PrivCheck only on systems you own or have explicit permission to audit.
Improper use may violate local laws or organizational policies.

AI Assistance Disclosure

This project was developed with the help of AI tools, including:

ChatGPT — for guidance on Python coding, project structure, and README drafting

Microsoft Copilot — for code snippets, automation logic, and formatting suggestions

All core functionality, testing, and integration were completed by the author.
