# 🔐 Advanced Security Audits & Final Deployment Security  
## DeveloperHub Corporation – Cybersecurity Internship  

---

## 👨‍💻 Internship Information

| Field | Information |
|------|-------------|
| Organization | DeveloperHub Corporation |
| Internship Program | DHC Cybersecurity Internship |
| Phase | Phase II |
| Week | Week 6 |
| Intern Name | Muhammad Umer |
| Intern ID | DHC 322 |

---

# 🎯 Goal

The goal of this task was to conduct **advanced security audits**, ensure compliance with **OWASP Top 10 security standards**, and prepare the application for **secure deployment**.

Tasks performed in this phase include:

- Security vulnerability scanning
- Web server security testing
- Linux system auditing
- OWASP Top 10 compliance verification
- Penetration testing using Metasploit
- Applying secure deployment practices

---

# 🌐 Target Application

Target used during testing:

```
http://testphp.vulnweb.com
```

This website is intentionally vulnerable and designed for **security testing practice and penetration testing learning**.

---

# ⚠️ Ethical Disclaimer

All testing performed in this project was conducted strictly for **educational purposes** as part of the **DeveloperHub Corporation Cybersecurity Internship**.

No unauthorized systems were targeted.

---

# 🔎 Step 1 — Security Audit Using OWASP ZAP

OWASP ZAP is a web application vulnerability scanner used to identify security weaknesses.

### Method Used

An automated scan was performed against the target web application.

### Findings

The scan detected several potential issues:

- Missing HTTP security headers
- Possible Cross-Site Scripting (XSS) points
- Weak input validation
- Potential injection attack surfaces

These issues suggest that the application requires stronger security controls.

---

# 🔎 Step 2 — Web Server Scan Using Nikto

Nikto is a web server vulnerability scanner used to identify misconfigurations and security weaknesses.

### Command Used

```bash
nikto -h http://testphp.vulnweb.com
```

### Findings

Nikto identified several issues including:

- Missing security headers
- Possible information disclosure
- Potential outdated software components

These findings indicate that attackers may gather server information if security measures are not implemented.

---

# 🔧 Step 3 — System Security Audit Using Lynis

Lynis is a Linux auditing tool used to evaluate system security and identify hardening opportunities.

### Command Used

```bash
sudo lynis audit system
```

### Example Output

```
Hardening index : 70
Warnings        : 4
Suggestions     : 20
```

### Observations

The audit recommended improvements in:

- System hardening
- Authentication policies
- Security monitoring configuration

---

# 📜 Step 4 — OWASP Top 10 Compliance Check

The application was analyzed according to **OWASP Top 10 security risks**.

| Risk | Status |
|-----|--------|
| Broken Access Control | Needs improvement |
| Cryptographic Failures | Low risk |
| Injection | SQL Injection detected |
| Insecure Design | Moderate risk |
| Security Misconfiguration | Detected |
| Vulnerable Components | Detected |
| Authentication Failures | Moderate risk |

---

# 🚀 Step 5 — Secure Deployment Practices

Secure deployment practices were implemented to improve system security.

## Automatic Security Updates

Commands used to enable system updates:

```bash
sudo apt update
sudo apt upgrade
sudo apt install unattended-upgrades
```

Enable automatic updates:

```bash
sudo dpkg-reconfigure unattended-upgrades
```

This ensures the system receives security patches automatically.

---

## Dependency Vulnerability Scanning

Dependencies were checked for security vulnerabilities.

Example commands:

```bash
npm audit
```

or

```bash
pip-audit
```

These tools detect insecure packages used in the project.

---

# 🐳 Docker Security Best Practices

Container security practices include:

- Using minimal container images
- Avoid running containers as root
- Regular vulnerability scanning

Example commands:

```bash
docker scan nginx
```

or

```bash
trivy image nginx
```

---

# ⚔ Step 6 — Final Penetration Testing Using Metasploit

Penetration testing was conducted using **Metasploit Framework**.

### Start Metasploit

```bash
msfconsole
```

---

### Module Used

```
auxiliary/scanner/http/http_version
```

This module detects the **web server version and backend technology**.

---

### Commands Executed

```bash
use auxiliary/scanner/http/http_version
set RHOSTS testphp.vulnweb.com
run
```

---

### Scan Result

```
44.228.249.3:80 nginx/1.19.0
Powered by PHP/5.6.40
```

---

# ⚠ Security Finding

The scan revealed that the server is running:

```
PHP 5.6.40
```

This version of PHP is **outdated and unsupported**, which increases the risk of security vulnerabilities.

---

# 🔐 Security Recommendations

To improve system security the following actions are recommended:

- Upgrade PHP to a supported version such as **PHP 8.x**
- Implement strong input validation
- Apply regular security updates
- Configure HTTP security headers
- Perform periodic vulnerability scans

---

# 🛠 Tools Used

| Tool | Purpose |
|-----|--------|
| OWASP ZAP | Web application vulnerability scanning |
| Nikto | Web server vulnerability scanning |
| Lynis | Linux system security auditing |
| Metasploit | Penetration testing |

---

# 📚 Skills Learned

During this project the following skills were developed:

- Web security auditing
- Vulnerability scanning
- Linux system hardening
- Secure deployment practices
- Penetration testing methodology

---

# 🏁 Conclusion

This project demonstrated how **advanced security auditing and penetration testing** help identify vulnerabilities before deploying applications.

By following OWASP best practices and performing regular security scans, organizations can significantly improve application security.

---

# 👨‍💻 Author

Muhammad Umer  
Cybersecurity Intern  
DeveloperHub Corporation  

Intern ID: **DHC 322**

---
