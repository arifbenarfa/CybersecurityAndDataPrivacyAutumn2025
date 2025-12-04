# 1️⃣ Introduction

**Tester(s):**  
- Name: Arif Ben Arfa

**Purpose:**  
- The purpose of this test was to identify security vulnerabilities in the Booking System registration page and related authentication functionality.

**Scope:**  
- Tested components: Registration page, input validation, basic authentication flow  
- Exclusions: Payment page, admin panel, booking management  
- Test approach: Black-box

**Test environment & dates:**  
- Start: 25.11.2025  
- End: 25.11.2025  
- Test environment details:  
  - OS: Windows 10  
  - Container: Docker (Linux container)  
  - Browser: Google Chrome  
  - Tools: OWASP ZAP, Burp Suite

**Assumptions & constraints:**  
- No valid user credentials provided
- Limited testing time


---

# 2️⃣ Executive Summary

**Short summary (1-2 sentences):**  
The Booking System registration page contains multiple serious security vulnerabilities that could allow attackers to compromise user data and manipulate the system.

**Overall risk level:** High

**Top 5 immediate actions:**  
1. Implement proper input validation and sanitization  
2. Enforce strong password policy  
3. Add CSRF protection  
4. Hide server information and version headers  
5. Rework session management
 

---

# 3️⃣ Severity scale & definitions

|  **Severity Level**  | **Description**                                                                                                              | **Recommended Action**           |
| -------------------- | ---------------------------------------------------------------------------------------------------------------------------- | -------------------------------- |
|      🔴 **High**     | A serious vulnerability that can lead to full system compromise or data breach (e.g., SQL Injection, Remote Code Execution). | *Immediate fix required*         |
|     🟠 **Medium**    | A significant issue that may require specific conditions or user interaction (e.g., XSS, CSRF).                              | *Fix ASAP*                       |
|      🟡 **Low**      | A minor issue or configuration weakness (e.g., server version disclosure).                                                   | *Fix soon*                       |
| 🔵 **Info** | No direct risk, but useful for system hardening (e.g., missing security headers).                                            | *Monitor and fix in maintenance* |


---

# 4️⃣ Findings

| ID  | Severity | Finding                        | Description                                                       | Evidence / Proof |
|-----|----------|--------------------------------|-------------------------------------------------------------------|------------------|
| F-01 | 🔴 High | SQL Injection possibility      | Input fields accept special characters like `' OR '1'='1`        | Manual testing |
| F-02 | 🟠 Medium | Missing CSRF protection      | Registration form does not use CSRF tokens                      | Source code / ZAP |
| F-03 | 🟡 Low  | Weak password policy           | System accepts very simple passwords such as `12345`            | Manual testing |
| F-04 | 🟡 Low  | Missing security headers       | No X-Frame-Options / X-Content-Type headers                      | ZAP Scan |
| F-05 | 🔵 Info | Server version disclosure       | Server exposes version info in HTTP headers                     | ZAP Scan |


---

# 5️⃣ OWASP ZAP Test Report (Attachment)

**ZAP Report Link:**  
https://github.com/arifbenarfa/CybersecurityAndDataPrivacyAutumn2025/blob/main/BookingSystem/Phase1/zap_report_round1.md

---

**Instructions (CMD version):**
1. Run OWASP ZAP baseline scan:  
   ```bash
   zap-baseline.py -t https://example.com -r zap_report_round1.html -J zap_report.json
   ```
2. Export results to markdown:  
   ```bash
   zap-cli report -o zap_report_round1.md -f markdown
   ```
3. Save the report as `zap_report_round1.md` and link it below.

---
> [!NOTE]
> 📁 **Attach full report:** → `check itslearning` → **Add a link here**

---