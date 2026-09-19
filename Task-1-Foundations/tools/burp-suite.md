# Burp Suite

> Web application security testing platform used to intercept, inspect, and modify HTTP/HTTPS requests.

---

## Objective

Understand the basic use of Burp Suite as an intercepting proxy for analyzing web application traffic in an authorized cybersecurity lab.

---

## 1. What is Burp Suite?

Burp Suite is a web application security testing platform that allows HTTP/HTTPS requests and responses to be intercepted and inspected.

It can be used for:

- HTTP request interception
- Request and response analysis
- Web traffic inspection
- Request modification
- Repeater-based testing
- Web application security assessment

---

## 2. Basic Workflow

A basic Burp Suite workflow is:

1. Start Burp Suite.
2. Configure or use the Burp browser.
3. Browse an authorized web application.
4. Intercept the HTTP request.
5. Inspect the request and response.
6. Modify and resend requests when required for authorized testing.

---

## 3. Practical Lab

The Burp Suite exercise was performed against the authorized Metasploitable 2 lab environment.

Target:

    http://192.168.100.20

The target was accessed through the Burp Suite browser.

---

## 4. Practical Verification

Burp Suite was configured to intercept HTTP traffic.

The Metasploitable 2 web application was accessed through the Burp browser.

An HTTP request was intercepted and inspected using:

    Proxy → Intercept

The captured request provided evidence that Burp Suite was successfully operating as an intercepting proxy.

---

## 5. Practical Evidence

Screenshot:

    screenshots/15-burpsuite-intercept.png

The screenshot provides evidence of an HTTP request intercepted by Burp Suite.

---

## Security Relevance

Burp Suite is useful for:

- Web application testing
- HTTP request analysis
- Session and parameter inspection
- Request manipulation
- Security assessment
- Identifying application-level security issues

---

## Verification Status

| Area | Status |
|---|---|
| Burp Suite startup | Completed |
| Burp browser access | Completed |
| HTTP traffic interception | Completed |
| Request inspection | Completed |
| Practical evidence | Completed |

---

## Conclusion

Burp Suite was used as an intercepting proxy to capture and inspect HTTP traffic from the authorized Metasploitable 2 web application.
