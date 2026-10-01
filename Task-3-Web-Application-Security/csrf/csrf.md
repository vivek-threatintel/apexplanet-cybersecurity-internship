# Cross-Site Request Forgery (CSRF)

## Overview

Cross-Site Request Forgery (CSRF) is a web application vulnerability in which a victim's authenticated browser can be induced to send an unintended state-changing request to an application.

This exercise was performed using the CSRF module of Damn Vulnerable Web Application (DVWA) in a controlled local laboratory environment.

---

## Lab Environment

- Kali Linux
- Apache HTTP Server
- PHP
- MariaDB
- Damn Vulnerable Web Application (DVWA)
- Firefox Web Browser

### Target

```
http://127.0.0.1/dvwa/
```

All testing was performed against the local DVWA instance.

---

## Objective

The objectives of this exercise were:

- Understand the CSRF vulnerability.
- Test the password-change functionality.
- Inspect the source code at different DVWA security levels.
- Compare the CSRF protection implemented at different security levels.

---

# 1. Password Change Request

The DVWA CSRF module was used to examine the password-change functionality.

The request was analyzed to understand how the application processes a password-change operation and whether additional request validation is present.

### Evidence

![CSRF Password Change](36-csrf-password-change.png)

**Evidence:** `36-csrf-password-change.png`

The screenshot documents the password-change functionality examined during the CSRF exercise.

---

# 2. Low Security Level — Source Code

The source code of the CSRF module was reviewed at the Low security level.

The purpose of this analysis was to understand how the application processes the password-change request and what request validation mechanisms are present.

### Evidence

![CSRF Low Security Source](37-csrf-source-low.png)

**Evidence:** `37-csrf-source-low.png`

The screenshot shows the source-code implementation at the Low security level.

---

# 3. Medium Security Level — Source Code

The source code was also reviewed at the Medium security level.

This allowed the request-handling implementation to be compared with the Low security implementation.

### Evidence

![CSRF Medium Security Source](37-csrf-medium-source.png)

**Evidence:** `37-csrf-medium-source.png`

The screenshot shows the source-code implementation at the Medium security level.

---

# 4. Security-Level Comparison

The CSRF implementations at different DVWA security levels were compared to identify changes in request validation and protection mechanisms.

### Evidence

The comparison was documented in:

```
38-csrf-compare-levels.pdf
```

The report provides the collected comparison of the different security-level implementations.

---

# 5. Security Analysis

CSRF protection is intended to ensure that a state-changing request was intentionally initiated by the legitimate user.

Common defensive mechanisms include:

- Anti-CSRF tokens
- SameSite cookie attributes
- Origin validation
- Referer validation where appropriate
- Re-authentication for sensitive operations

The exact protection mechanism depends on the application's implementation.

---

# 6. Evidence Summary

| Evidence | Description |
|---|---|
| `36-csrf-password-change.png` | Password-change request testing |
| `37-csrf-source-low.png` | CSRF source code at Low security |
| `37-csrf-medium-source.png` | CSRF source code at Medium security |
| `38-csrf-compare-levels.pdf` | Comparison of CSRF security levels |

---

## Conclusion

The CSRF exercise examined the password-change functionality and the corresponding source code at different DVWA security levels.

The comparison demonstrated how the application's request-processing and protection mechanisms can differ between security levels.

All testing was performed against the local DVWA environment.
```
