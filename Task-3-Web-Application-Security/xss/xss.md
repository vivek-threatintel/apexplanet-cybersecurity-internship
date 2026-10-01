# Cross-Site Scripting (XSS)

## Overview

Cross-Site Scripting (XSS) is a web application vulnerability that occurs when an application processes user-controlled input in a way that allows client-side script content to be executed in a user's browser.

This exercise was performed using the XSS modules of Damn Vulnerable Web Application (DVWA) in a controlled local laboratory environment.

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

- Understand Cross-Site Scripting vulnerabilities.
- Demonstrate Stored XSS.
- Demonstrate Reflected XSS.
- Understand the difference between stored and reflected input.
- Observe how insufficient input handling can lead to script execution.

---

# 1. Stored XSS

Stored XSS occurs when attacker-controlled input is stored by the application and later rendered to users.

In the DVWA Stored XSS module, user-supplied input was submitted through the application and the resulting behavior was observed when the stored content was rendered.

### Evidence

**Evidence:** `34-stored-xss.png`

The screenshot documents the Stored XSS test performed against the DVWA application.

---

# 2. Reflected XSS

Reflected XSS occurs when user-controlled input is immediately reflected by the application in its response instead of being permanently stored.

The DVWA Reflected XSS module was used to test this behavior.

### Evidence

**Evidence:** `35-reflected-xss.png`

The screenshot documents the Reflected XSS test performed against the DVWA application.

---

# 3. Stored XSS vs Reflected XSS

| Characteristic | Stored XSS | Reflected XSS |
|---|---|---|
| Input storage | Stored by the application | Not permanently stored |
| Execution | Occurs when stored content is rendered | Occurs when the crafted request is processed |
| Delivery | Content can be delivered through the affected application | Usually requires the crafted request to reach the victim |
| Persistence | Persistent | Non-persistent |

---

# 4. Security Impact

XSS can allow attacker-controlled client-side code to execute in the security context of the affected web application.

Depending on the application's design and browser security controls, the impact can include:

- Manipulation of page content
- Unauthorized actions performed through the victim's session
- Exposure of accessible client-side information
- Phishing or interface manipulation

The actual impact depends on the application's implementation and available browser-side controls.

---

# 5. Mitigation

Recommended protections include:

1. Apply context-aware output encoding.
2. Validate and constrain user input where appropriate.
3. Avoid inserting untrusted input directly into HTML or JavaScript contexts.
4. Use appropriate Content Security Policy (CSP) controls.
5. Use secure framework features for automatic output escaping.
6. Review all locations where user-controlled data is rendered.

Input validation alone should not be treated as the primary XSS defense. Context-appropriate output encoding and safe rendering practices are important defensive controls.

---

# 6. Evidence Summary

| Evidence | Description |
|---|---|
| `34-stored-xss.png` | Stored XSS demonstration |
| `35-reflected-xss.png` | Reflected XSS demonstration |

---

## Conclusion

The XSS exercise demonstrated two common forms of Cross-Site Scripting: Stored XSS and Reflected XSS.

The practical tests showed the difference between input that is stored and later rendered and input that is reflected directly in an application's response.

The exercise was performed against the local DVWA environment for controlled security testing.
