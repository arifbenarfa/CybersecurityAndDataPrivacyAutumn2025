# 🛠️ Penetration Test Report – Booking System (Phase 1)

---

## 1️⃣ Introduction

### **Tester(s)**  
- Name: Arif Ben Arfa

### **Purpose**  
The purpose of this penetration test is to identify security vulnerabilities in the Booking System registration page and evaluate the security posture of the application during Phase 1.

### **Scope**
**Tested components:**
- Registration page  
- Authentication-related requests  
- Client-side validation  
- Server responses  

**Excluded from scope:**
- Admin panel  
- Payment flow  
- Full backend source code  

**Test approach:**  
Gray-box testing

### **Test environment & dates**
- **Start:** 27.11.2025  
- **End:** 04.12.2025  

**Environment details:**
- OS: Kali Linux + Windows 11  
- Browser: Firefox  
- Tools: OWASP ZAP, curl, browser devtools  
- Dockerized Booking System (teacher-provided environment)

### **Assumptions & constraints**
- Test performed locally in a controlled Docker lab.
- No access to backend code.
- Limited to functionalities available in Phase 1 only.

---

## 2️⃣ Executive Summary

### Summary  
Testing revealed several vulnerabilities in the registration flow, including missing validation, improper error handling, and exposure of sensitive information. The overall security posture is **weak**.

### **Overall risk level: 🔴 High**

### **Top 5 immediate actions**
1. Implement backend validation for all registration fields  
2. Add strong password requirements  
3. Sanitize all user input (prevent injection attacks)  
4. Add missing security headers  
5. Fix inconsistent HTTP error responses  

---

## 3️⃣ Severity Scale & Definitions

| Severity | Description | Recommended Action |
|---------|-------------|-------------------|
| 🔴 **High** | Serious vulnerability leading to full compromise (e.g., SQL injection) | Fix immediately |
| 🟠 **Medium** | Vulnerability requiring some conditions (e.g., XSS, CSRF) | Fix as soon as possible |
| 🟡 **Low** | Minor weakness or configuration issue | Fix soon |
| 🔵 **Info** | No direct impact; informational | Improve in next maintenance cycle |

---

## 4️⃣ Findings

| ID | Severity | Finding | Description | Evidence |
|----|----------|---------|-------------|----------|
| **F-01** | 🔴 High | No server-side input validation | Registration accepts invalid emails, empty fields, and malformed data | Screenshot in ZAP report |
| **F-02** | 🟠 Medium | Missing security headers | Application lacks CSP, HSTS, X-Frame-Options | ZAP report alerts |
| **F-03** | 🟠 Medium | Weak password policy | Password “12345” accepted without rejection | Manual test |
| **F-04** | 🟡 Low | Technology disclosure | Server reveals framework information in headers | Burp/ZAP response info |
| **F-05** | 🔵 Info | Verbose error messages | Backend exposes unnecessary technical details | Browser console / ZAP |

> Maximum 5 findings included as required.

---

## 5️⃣ OWASP ZAP Test Report (Attachment)

Your full ZAP scan report is included in this repository.

📄 **ZAP Report (Markdown):**  
[zap_report_round1.md](./zap_report_round1.md)

The ZAP scan was executed following the teacher’s instructions:

```bash
zap-baseline.py -t http://localhost:3000 -r zap_report_round1.html -J zap_report.json
```

Converted to Markdown:

```bash
pandoc zap_report_round1.html -o zap_report_round1.md
```

---

## ✔️ End of Report

