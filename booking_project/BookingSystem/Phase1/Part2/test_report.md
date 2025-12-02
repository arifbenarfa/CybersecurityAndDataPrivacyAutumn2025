# Booking System – Phase 1: Part 2 – Test Report

## Tested by
Student

## Date
02 December 2025

## Target URL
http://localhost:8001

---

## 1. EnvironmentS

The following containers were running during the test:

- cybersec-web-phase1-part2 (port 8001)
- cybersec-db-phase1-part2 (port 5433)

Both containers were verified as running using:
docker ps

---

## 2. Functional Testing (Browser)

The application was accessed in a browser at:

http://localhost:8001

Result:
- The page loads correctly
- The interface is visible
- The login button appears but is not required for this phase

| Test Case | Action | Result |
|------|------|------|
| FT1 | Open homepage | ✅ Page loaded successfully |
| FT2 | Click links | ✅ Navigation works |
| FT3 | Click login button | ⚠ Button does not respond (known issue, ignored for this phase) |

---

## 3. Security Observation

No authentication was required to access the main page.

Potential risks in a real system:
- Missing authentication checks
- Missing security headers
- Possible lack of access control

These issues should be addressed before production use.

---

## 4. Summary

Phase 1 – Part 2 was successfully started using Docker Compose.
The application container and database container are working correctly.
The website is accessible at http://localhost:8001.

No further technical changes were required for this phase.

---

## 5. Conclusion

This part of the assignment is COMPLETE.

The environment is running and accessible.
Basic functional testing has been performed.
Documentation is completed in this file.

## 2.2 Functional Issue – Login Button Not Working

**URL:** http://localhost:8001  

**Issue:**  
The Login button is visible on the page but sometimes cannot be clicked or does not redirect to another page.

**Impact:**  
Users are unable to access authentication functionality.

**Risk Level:** Medium  

### Possible causes
- Missing or broken JavaScript event listener
- CSS property blocking interaction (pointer-events: none)
- Broken link or missing route

### Recommendation
- Check `/static/index.js` for click handler
- Confirm button is not disabled or blocked in CSS
- Verify link or action for the login page

