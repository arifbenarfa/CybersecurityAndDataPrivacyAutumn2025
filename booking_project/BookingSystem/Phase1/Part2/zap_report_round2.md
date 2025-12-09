# ZAP Report – Round 2

## Application Tested
Booking System – Phase 1 Part 2  
URL: http://localhost:8001

## Purpose
The purpose of this test was to re-run OWASP ZAP scans on the updated
Booking System to verify whether previously reported security issues
have been fixed.

## Testing Tool
- Tool used: OWASP ZAP
- Scan type: Automated Scan
- Date: 27 November 2025

---

## Summary of Findings

The following issues were identified during the second scan:

1. **Missing Anti-Clickjacking Header**
   - Risk Level: Medium
   - Status: NOT FIXED
   - Description: The application is still vulnerable to clickjacking attacks
     because the `X-Frame-Options` or `Content-Security-Policy` header is missing.

2. **X-Content-Type-Options Header Missing**
   - Risk Level: Low
   - Status: NOT FIXED
   - Description: The server does not include the `X-Content-Type-Options: nosniff`
     header, which can allow MIME-type sniffing attacks.

3. **CSP Header Not Set**
   - Risk Level: Medium
   - Status: NOT FIXED
   - Description: The Content Security Policy header has not been implemented.

4. **Server Leaks Version Information**
   - Risk Level: Low
   - Status: NOT FIXED
   - Description: Server headers expose technology and version information.

5. **Cookies Missing HttpOnly/Secure Flags**
   - Risk Level: Low
   - Status: NOT FIXED
   - Description: Some cookies do not have secure flags properly configured.

---

## Conclusion

After re-running the scan, the majority of previously reported vulnerabilities
still exist in the system. This means that no significant security fixes
have been implemented in the current version of the Booking System.

Further action is required by the development team to implement the
recommended security headers and cookie configurations.
