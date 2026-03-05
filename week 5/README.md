# 🛡️ Ethical Hacking & Exploiting Vulnerabilities
## DeveloperHub Corporation – Cybersecurity Internship

---

![Cybersecurity](https://img.shields.io/badge/Cybersecurity-Ethical%20Hacking-red)
![Internship](https://img.shields.io/badge/Internship-DeveloperHub%20Corporation-blue)
![Phase](https://img.shields.io/badge/Phase-II-green)
![Week](https://img.shields.io/badge/Week-5-orange)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

---

# 👨‍💻 Internship Information

| Field | Information |
|------|-------------|
| Organization | **DeveloperHub Corporation** |
| Internship Phase | **Phase II** |
| Week | **Week 5** |
| Task | **Ethical Hacking & Exploiting Vulnerabilities** |
| Intern Name | **Muhammad Umer** |
| Intern ID | **DHC 322** |

---

# 🎯 Task Objective

The purpose of this task was to understand and apply **ethical hacking techniques** to identify vulnerabilities in a web application.

During this task the following activities were performed:

- Reconnaissance of the target system
- Directory and endpoint discovery
- SQL Injection testing and exploitation
- CSRF vulnerability scanning
- Understanding how vulnerabilities impact security
- Learning secure coding practices to mitigate these issues

---

# 🌐 Target Application

The target used for testing was an intentionally vulnerable application:

http://testphp.vulnweb.com/


This website is designed for **security testing and educational purposes**.

It contains multiple intentionally vulnerable components used by security researchers and students to practice penetration testing.

---

# ⚠️ Ethical Disclaimer

All testing was conducted **only for educational and internship purposes** on a **vulnerable test environment**.

No unauthorized systems were targeted.

---

# 🔎 Phase 1 — Reconnaissance

Reconnaissance is the process of collecting information about the target system before attempting any exploitation.

In this phase I used **Nmap** to discover open ports and services running on the server.

### Tool Used


### Command Used

```bash
nmap -sV testphp.vulnweb.com

PORT   STATE SERVICE VERSION
80/tcp open  http    Apache Web Server

## 📂 Phase 2 — Directory Enumeration

After identifying the web service, the next step was discovering hidden directories and files.

This was done using **Gobuster**.

Directory enumeration helps find hidden endpoints, login pages, and vulnerable parameters.

### 🔧 Tool Used


### 💻 Command Used
```bash
gobuster dir -u http://testphp.vulnweb.com -w /usr/share/wordlists/dirb/common.txt

/login.php
/search.php
/cart.php
/categories.php
/listproducts.php

💉 Phase 3 — SQL Injection Testing

SQL Injection is one of the most common web application vulnerabilities.

It occurs when an application does not properly sanitize user input before using it in database queries.

To test for SQL Injection I used SQLMap, an automated SQL Injection exploitation tool.

🔧 Tool Used
sqlmap
🎯 Target Parameter
http://testphp.vulnweb.com/listproducts.php?cat=1
💻 Command Used
sqlmap -u "http://testphp.vulnweb.com/listproducts.php?cat=1" --dbs
📊 Result

SQLMap successfully identified a SQL Injection vulnerability.

It was able to enumerate databases including:

information_schema
acuart

Further commands can be used to enumerate tables and dump database data.

Example Command
sqlmap -u "http://testphp.vulnweb.com/listproducts.php?cat=1" -D acuart --tables

This demonstrates that the application does not properly validate input parameters.

🧪 Phase 4 — CSRF Vulnerability Testing

Cross-Site Request Forgery (CSRF) occurs when attackers trick a user into performing actions on a website where they are authenticated.

To detect potential CSRF vulnerabilities I used xsrfprobe.

🔧 Tool Used
xsrfprobe
💻 Command Used
xsrfprobe -u http://testphp.vulnweb.com
📊 Result

The scan revealed that some forms do not implement CSRF tokens, which means malicious requests could potentially be executed.

This vulnerability allows attackers to perform actions on behalf of authenticated users.


i want this in one time one way file not part
