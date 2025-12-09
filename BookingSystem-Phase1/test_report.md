# Booking System — Penetration & Functionality Test Report (Phase 1)

**Project:** Booking System  
**Student:** Arif Ben Arfa  
**Repository:** https://github.com/arifbenarfa/CybersecurityAndDataPrivacyAutumn2025/tree/main/BookingSystem-Phase1  
**Date:** 2025-12-09

---

## 1️⃣ Introduction

**Tester(s):**  
- Arif Ben Arfa

**Purpose:**  
- Identify security vulnerabilities and functional issues in the Booking System registration page and verify registration functionality.

**Scope:**  
- Tested components: Registration page and server responses related to registration (POST /register).  
- Exclusions: Payment flow, admin panel, production systems.  
- Test approach: Black-box testing (manual + automated scans with OWASP ZAP).

**Test environment & dates:**  
- Start: 2025-11-25  
- End: 2025-12-09  
- Environment details:
  - Host OS: Windows 10 / Windows 11 (local VM)
  - Application: Local Docker instance (as provided in course materials)
  - Browser: Google Chrome (latest)
  - Tools: OWASP ZAP (scan + active testing), curl, PowerShell, Notepad

**Assumptions & constraints:**  
- No privileged credentials were provided.  
- Testing limited to local lab environment.  
- Timebox for Phase 1: basic registration-focused testing.

---

## 2️⃣ Executive Summary

**Short summary (1-2 sentences):**  
The registration page contains multiple input validation and configuration weaknesses, including reflected XSS and missing CSRF protection. These issues allow an attacker to execute client-side scripts and perform cross-site attacks.

**Overall risk level:** High

**Top 5 immediate actions:**  
1. Implement server-side input validation and output encoding.  
2. Add anti-CSRF protection to all state-changing forms.  
3. Enforce a strong password policy (length + complexity).  
4. Harden session management and review cookie flags (HttpOnly, Secure, SameSite).  
5. Remove or hide detailed server/version headers and error stack traces.

---

## 3️⃣ Severity scale & definitions

|  **Severity Level**  | **Description**                                                                                                              | **Recommended Action**           |
| -------------------- | ---------------------------------------------------------------------------------------------------------------------------- | -------------------------------- |
| 🔴 **High**          | Serious vulnerability that can lead to data breach or system compromise (e.g., SQLi, RCE).                                   | Immediate fix required.          |
| 🟠 **Medium**        | Vulnerability that can be exploited with specific conditions (e.g., XSS, CSRF).                                               | Fix ASAP.                        |
| 🟡 **Low**           | Minor issues or configuration weaknesses with low immediate impact.                                                         | Fix soon.                        |
| 🔵 **Info**          | Informational findings useful for hardening (e.g., missing security headers).                                                | Monitor/fix in maintenance.      |

---

## 4️⃣ Findings

### F-01 — Reflected Cross-Site Scripting (XSS) in username field  
- **Severity:** 🔴 High  
- **Description:** User-supplied input in the registration username field is reflected in the response without proper HTML encoding.  
- **Reproduction steps:**  
  1. Open registration page.  
  2. Submit username: <script>alert('XSS')</script> with valid password.  
  3. Observe the alert popup or that the script is present in returned HTML.  
- **Evidence:** request/response snippet saved in ZAP report (see linked ZAP report).  
- **Impact:** Attackers can execute scripts in other users' browsers, steal cookies or perform UI redress/phishing.  
- **Remediation:** Escape/encode output on the server side. Use a templating engine that performs automatic context-aware escaping.

---

### F-02 — Missing CSRF protection on registration form  
- **Severity:** 🟠 Medium  
- **Description:** Registration form lacks an anti-CSRF token or other CSRF mitigation.  
- **Reproduction steps:**  
  1. Construct a malicious HTML page performing a POST to the registration endpoint.  
  2. Host the page; when a victim visits the page, the POST executes.  
- **Evidence:** No hidden CSRF token found in registration form fields (inspection / ZAP passive scan).  
- **Impact:** Cross-site requests may create unwanted registrations or perform actions on behalf of users.  
- **Remediation:** Implement synchronizer token pattern or use SameSite cookies and server-side token checks.

---

### F-03 — Weak password policy accepted  
- **Severity:** 🟡 Low  
- **Description:** System accepts weak passwords (e.g., "12345" or commonly used passwords).  
- **Reproduction steps:** Enter a simple password and complete registration.  
- **Evidence:** Successful registration with weak password (screenshots in evidence or ZAP logs).  
- **Impact:** Increases risk of account takeover via credential stuffing.  
- **Remediation:** Enforce minimum length and complexity; use server-side validation and password strength checks.

---

### F-04 — Missing security headers (X-Frame-Options, X-Content-Type-Options)  
- **Severity:** 🟡 Low  
- **Description:** Responses do not include common security headers.  
- **Reproduction steps:** Inspect HTTP response headers via browser dev tools or ZAP.  
- **Evidence:** Header list in ZAP report.  
- **Impact:** Potential for clickjacking or content sniffing attacks.  
- **Remediation:** Add X-Frame-Options: DENY or Content-Security-Policy and X-Content-Type-Options: nosniff.

---

### F-05 — Server version disclosure in headers  
- **Severity:** 🔵 Info  
- **Description:** Server exposes version information in response headers.  
- **Reproduction steps:** View response headers.  
- **Evidence:** Header output in ZAP.  
- **Impact:** Information disclosure helps attackers craft targeted exploits.  
- **Remediation:** Remove version strings from server headers and error pages.

---

## 5️⃣ OWASP ZAP Test Report (Attachment)

**ZAP Report Link (full scan output in Markdown):**  
[zap_report_round1.md](./zap_report_round1.md)

> Note: The ZAP scan contains request/response evidence, passive and active alerts and is included in the repository as zap_report_round1.md.

---

## 6️⃣ Functional Test Cases (Registration)

- **TC-01 — Valid registration**  
  - Steps: Fill valid username, valid password, submit.  
  - Expected: Registration success page or redirect to login.  
  - Actual: Registration completed (PASS).  

- **TC-02 — Empty fields validation**  
  - Steps: Submit with empty username and/or password.  
  - Expected: Server-side validation error and user-friendly message.  
  - Actual: Proper validation shown (or note failures if applicable).

- **TC-03 — Long input boundary test**  
  - Steps: Submit username with 2000 characters.  
  - Expected: Server rejects with validation or truncates safely.  
  - Actual: Check for server error (500) or successful handling — document result.

- **TC-04 — Special characters / encoding**  
  - Steps: Submit HTML/script characters in username.  
  - Expected: Data sanitized/encoded; no script execution.  
  - Actual: Observed reflected XSS (see F-01).

---

## 7️⃣ Conclusion

The registration page contains multiple security weaknesses that should be prioritized: fix XSS and CSRF first, then harden password policy and security headers. After remediation, re-scan using OWASP ZAP and re-test manually.

---

## 8️⃣ Appendix

**Environment & tools:**  
- OWASP ZAP version: (see zap_report_round1.md header)  
- Browser: Google Chrome  
- OS: Windows 10/11  
- Notes: Local Docker lab based on course materials.

**Full evidence & logs:** See zap_report_round1.md for complete scan output, request/response pairs, and automated alerts.

---
