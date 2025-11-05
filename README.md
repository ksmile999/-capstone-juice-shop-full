# 🧠 Capstone Project — Ethical Hacking of an E-Commerce Application (OWASP Juice Shop)

## 📌 Project Overview
This capstone project demonstrates a **comprehensive vulnerability assessment** and **ethical hacking engagement** performed on the **OWASP Juice Shop** — an intentionally vulnerable e-commerce web application used for cybersecurity training.

The purpose of this project is to **identify, exploit, and document security vulnerabilities** following professional penetration-testing methodologies while maintaining ethical boundaries and safe lab practices.

---

## 🎯 Objectives
- Identify and analyze vulnerabilities across multiple web attack categories.  
- Demonstrate real-world exploitation and data exposure techniques.  
- Evaluate the security impact and risk severity of each finding.  
- Recommend actionable remediations aligned with **OWASP Top 10 (2021)**.  
- Strengthen technical and reporting skills in ethical hacking.

---

## ⚙️ Environment Setup
| Component | Details |
|------------|----------|
| **Target Application** | OWASP Juice Shop (Local Instance) |
| **Target URL** | `http://192.168.249.141:3000` |
| **Operating System** | Kali Linux 2024 |
| **Testing Tools** | Burp Suite, OWASP ZAP, DirBuster, Nmap, CyberChef, Turbo Intruder |
| **Browser Used** | Firefox / Chrome |
| **Testing Type** | Black-box (Unauthenticated) |
| **Network Mode** | Bridged Adapter |

> ⚠️ *All penetration testing activities were conducted ethically within an isolated lab environment.*

---

## 🧩 Methodology
The assessment followed both the **OWASP Testing Guide** and the **PTES (Penetration Testing Execution Standard)** methodology:

1. **Information Gathering** — OSINT, network scanning, and directory enumeration.  
2. **Vulnerability Analysis** — Identifying flaws through Burp Suite and manual review.  
3. **Exploitation** — Executing and validating each vulnerability safely.  
4. **Post-Exploitation** — Assessing privilege escalation and data sensitivity.  
5. **Reporting & Remediation** — Documenting findings and mitigation strategies.

---

## 📁 Repository Structure

---

## ⚔️ Exploitation Highlights
Each vulnerability was exploited ethically and verified in a controlled environment.  
All technical details are documented in the `/vulnerabilities/` folder.

| **Category** | **Example Vulnerability** | **Evidence Screenshot** |
|---------------|----------------------------|--------------------------|
| Injection Attacks | Admin Login Bypass | ![SQLi](assets/screenshots/exploitation/sql_injection_login.png) |
| Broken Authentication | Password Reset Manipulation | ![Auth](assets/screenshots/exploitation/broken_auth_password_reset.png) |
| Broken Access Control | Direct Admin Panel Access | ![Access](assets/screenshots/exploitation/access_control_admin_panel.png) |
| Sensitive Data Exposure | Forgotten Developer Backup | ![Data](assets/screenshots/exploitation/forgotten_dev_backup.png) |
| Security Misconfiguration | Null Byte File Type Evasion | ![Upload](assets/screenshots/exploitation/nullbyte_upload_bypass.png) |
| Cryptographic Failures | MD5 Password Cracking | ![Crypto](assets/screenshots/exploitation/md5_password_crack.png) |
| Broken Anti-Automation | Hidden Language Access | ![Automation](assets/screenshots/exploitation/extra_language_hidden.png) |
| Vulnerable Components | Legacy API Access | ![Legacy](assets/screenshots/exploitation/deprecated_interface.png) |
| Information Disclosure | YouTube OSINT Password Reset | ![OSINT](assets/screenshots/exploitation/bjorn_pet_osint.png) |

---

## 🏁 Flag Challenges Captured
A total of **six Juice Shop challenges** were successfully identified and solved.

| **Flag #** | **Challenge Name** | **Method Used** |
|:-----------:|--------------------|------------------|
| 1 | Zero Stars (Improper Input Validation) | Intercept feedback request → set rating = 0 |
| 2 | Forgotten Developer Backup | Download `package.json.bak%2500.md` via null-byte injection |
| 3 | Login Admin (SQL Injection) | Payload → `admin' OR 1=1--` |
| 4 | Five-Star Feedback Deletion | Delete review from admin endpoint |
| 5 | Weird Crypto | Submit comment `MD5` → trigger crypto challenge |
| 6 | Easter Egg / Nested Easter Egg | Decode `Base64 + ROT13` from `eastere.gg` |

---

## ⚙️ Technical Workflow
1. **Reconnaissance & Enumeration** — `nmap`, `DirBuster` to identify open ports and endpoints.  
2. **Vulnerability Testing** — Manual payload crafting using Burp Suite & CyberChef.  
3. **Exploitation** — Reproducing flaws (SQLi, Broken Auth, File Upload Bypass).  
4. **Privilege Escalation** — Accessing restricted data or admin panels.  
5. **Post-Exploitation Review** — Analyzing risks and data exposure.  
6. **Reporting & Mitigation** — Compiling detailed remediation advice.

---

## 🔐 Vulnerability Overview
| **Category** | **Example Issues** | **OWASP Top 10 Reference** |
|---------------|--------------------|------------------------------|
| Improper Input Validation | Zero-Star Feedback Challenge | Broken Access Control |
| SQL Injection | Login Admin / Database Schema Extraction | Injection |
| Broken Authentication | Weak Password Policy & Reset Flow | Identification & Auth Failures |
| Sensitive Data Exposure | `/ftp` backup file leaks | Cryptographic Failures |
| Broken Access Control | Forged Review / Admin Panel Access | Broken Access Control |
| File Upload Bypass | Null Byte / MIME Spoofing | Security Misconfiguration |
| Weak Cryptography | Deprecated MD5 Usage (Weird Crypto) | Cryptographic Failures |

---

## 🛡️ Security Recommendations
- ✅ Implement **server-side input validation** for all parameters.  
- ✅ Use **parameterized queries / ORM frameworks** to mitigate SQL Injection.  
- ✅ Enforce **strong password policies** and enable **MFA**.  
- ✅ Adopt **role-based access control (RBAC)** for authorization.  
- ✅ Remove sensitive or backup files from web directories.  
- ✅ Use **modern cryptographic standards** (SHA-256, AES-256).  
- ✅ Employ a **Web Application Firewall (WAF)** to detect injection attempts.  
- ✅ Regularly **update third-party dependencies** and perform patch management.

---

## 📄 Documentation
The complete report includes:
- Step-by-step exploitation evidence.  
- Burp Suite request/response captures.  
- Detailed risk assessments.  
- Mitigation guidance for each vulnerability.  

📘 **[View Full Report (PDF)](report/Capstone_Vulnerability_Assessment_Final.pdf)**

---

## 🖼️ Report Preview
![Report Cover](assets/screenshots/report/report_cover.png)

---

## 👤 Author
**Oppong Isaac**  
Cyber Security & Ethical Hacking Capstone Project  
November 2025  

---

## ⚖️ Ethical Disclaimer
All testing was conducted in a **controlled lab environment** on OWASP Juice Shop.  
The techniques and methods demonstrated are for **educational purposes only**.  
Do **not** perform these activities on unauthorized systems or networks.

---
