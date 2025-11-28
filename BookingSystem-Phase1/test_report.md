\# Booking System – Phase 1: Registration Page Test Report



\## Tested by

Student



\## Date

27 November 2025



\## Target URL

http://localhost:8000/register



\## Testing Tools Used

\- Manual testing (browser)

\- OWASP ZAP (Automated Scan)



---



\## 1. Functional Testing (Registration Page)



| Test Case | Input | Expected Result | Actual Result |

|------|------|------|------|

| TC1 | Valid data | User is registered | ✅ Success |

| TC2 | Empty fields | Error message | ❌ Error occurred |

| TC3 | Invalid email | Validation warning | ❌ Error occurred |

| TC4 | Very long input | Should reject | ❌ Error occurred |



---



\## 2. Security Testing – OWASP ZAP



An automated security scan was performed using \*\*OWASP ZAP\*\*.



\### 2.1 Main Findings



\*\*Issue:\*\* Missing Anti-clickjacking Header  

\*\*URL:\*\* http://localhost:8000/register  

\*\*Risk Level:\*\* Medium  



The application does not include protection against clickjacking attacks.  

Security headers such as `X-Frame-Options` or `Content-Security-Policy` are missing.



---



\## 3. Vulnerability Summary



| Vulnerability | Risk |

|------|------|

| Missing Anti-Clickjacking Header | Medium |



---



\## 4. Recommendations



\- Add `X-Frame-Options: DENY`

\- Add `Content-Security-Policy: frame-ancestors 'none'`

\- Improve form validation and error messages



---



\## 5. ZAP Report



See the attached file in this folder:



`2025-11-27-ZAP-Report-.html`



---



\## 6. Conclusion



The registration page contains security weaknesses and needs improvement

before production use.



