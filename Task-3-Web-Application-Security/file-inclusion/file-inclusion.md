# File Inclusion

## Overview

File Inclusion is a web application vulnerability that occurs when an application uses user-controlled input to determine which file is loaded or included.

This exercise was performed using the File Inclusion module of Damn Vulnerable Web Application (DVWA) in a controlled local laboratory environment.

The exercise covered:

- File Inclusion configuration
- Local File Inclusion (LFI)
- Reading a local file
- Remote File Inclusion (RFI)

---

## Lab Environment

- Kali Linux
- Apache HTTP Server
- PHP
- MariaDB
- Damn Vulnerable Web Application (DVWA)
- Firefox Web Browser
- Python HTTP server for the RFI test

### Target

```
http://127.0.0.1/dvwa/
```

All testing was performed against the local DVWA instance.

---

## Objective

The objectives of this exercise were:

- Understand the File Inclusion vulnerability.
- Examine the File Inclusion configuration.
- Test Local File Inclusion.
- Demonstrate access to a local file through the vulnerable parameter.
- Test Remote File Inclusion using a controlled local HTTP server.
- Understand the role of PHP configuration in File Inclusion behavior.

---

# 1. File Inclusion Configuration

The File Inclusion functionality was first enabled and verified in the DVWA environment.

The PHP configuration was adjusted to allow the functionality required for the controlled lab exercise.

### Evidence

![File Inclusion Enabled](38-file-inclusion-enabled.png)

**Evidence:** `38-file-inclusion-enabled.png`

The screenshot documents the File Inclusion functionality/configuration used during the exercise.

---

# 2. File Inclusion Test

The DVWA File Inclusion module uses the `page` parameter to determine which resource is loaded.

The parameter was tested to understand how user-controlled input affects the file-loading behavior.

### Evidence

![File Inclusion File Test](38-file-inclusion-file1.png)

**Evidence:** `38-file-inclusion-file1.png`

The screenshot documents the File Inclusion test performed in DVWA.

---

# 3. Local File Inclusion (LFI)

Local File Inclusion occurs when an application allows a user-controlled parameter to reference files available on the local system.

A local system file was used as the controlled test target.

### Evidence

![LFI Sensitive File](39-lfi-sensitive-file.png)

**Evidence:** `39-lfi-sensitive-file.png`

The screenshot demonstrates successful inclusion of a local file through the vulnerable File Inclusion functionality.

A second screenshot documents the local file inclusion test:

![Local File Inclusion](40-fi-local-file-inclusion.png)

**Evidence:** `40-fi-local-file-inclusion.png`

---

# 4. Remote File Inclusion (RFI)

Remote File Inclusion occurs when an application allows a remotely supplied resource to be included.

For the controlled laboratory test, a PHP test file was hosted from a local HTTP server and supplied to the DVWA File Inclusion functionality.

### Evidence

![RFI Test](40-rfi-test.png)

**Evidence:** `40-rfi-test.png`

The screenshot documents the Remote File Inclusion test using the controlled local resource.

---

# 5. PHP Configuration

The RFI test depended on the relevant PHP configuration.

The Apache PHP configuration was checked and `allow_url_include` was enabled for the controlled exercise.

This configuration determines whether PHP is permitted to include resources referenced through URL-based wrappers.

The configuration was used only within the local DVWA laboratory environment.

---

# 6. Security Analysis

File Inclusion vulnerabilities can occur when applications use untrusted input to determine which files or resources are loaded without adequate validation.

Potential impact depends on the application's configuration and the privileges available to the web server process.

Possible consequences can include:

- Unauthorized access to local files
- Exposure of sensitive application information
- Inclusion of unintended resources
- In some configurations, execution of attacker-controlled code

---

# 7. Mitigation

Recommended defensive controls include:

1. Avoid using unrestricted user input to determine file paths.
2. Use an allowlist of permitted files or resources.
3. Validate and normalize file paths.
4. Avoid unnecessary remote file inclusion functionality.
5. Disable `allow_url_include` when it is not required.
6. Apply least-privilege permissions to web application files.
7. Keep sensitive files outside web-accessible locations where practical.

---

# 8. Evidence Summary

| Evidence | Description |
|---|---|
| `38-file-inclusion-enabled.png` | File Inclusion configuration |
| `38-file-inclusion-file1.png` | File Inclusion test |
| `39-lfi-sensitive-file.png` | Local File Inclusion demonstration |
| `40-fi-local-file-inclusion.png` | LFI test |
| `40-rfi-test.png` | Remote File Inclusion test |

---

## Conclusion

The File Inclusion exercise demonstrated how user-controlled file parameters can affect application file-loading behavior.

Local File Inclusion was tested using a local system file, while Remote File Inclusion was tested using a controlled locally hosted PHP resource.

The exercise also demonstrated the relationship between File Inclusion behavior and PHP configuration.

All testing was performed against the local DVWA environment.
```
