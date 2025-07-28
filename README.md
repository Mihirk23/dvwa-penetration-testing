# DVWA Penetration Testing


This repository contains documented exploitation of common web vulnerabilities using **DVWA (Damn Vulnerable Web Application)**. The goal is to demonstrate hands-on skills in offensive security, including brute-force, command injection, RCE via file upload, SQL injection, and XSS attacks.


## Environment Setup

- **Platform**: Docker container running DVWA
- **OS**: Kali Linux
- **DVWA URL**: http://localhost:8080
- **Security Level**: Low
- **Tools Used**:
  - Burp Suite
  - Nmap
  - Hydra
  - Firefox Dev Tools
  - PHP Payloads


## Exploited Vulnerabilities

### 1. Brute Force (Login Bypass)
- **Tool**: Hydra
- **Target**: `/vulnerabilities/brute/`
- **Result**: Multiple valid passwords discovered for `admin` user.
  
**Screenshots**:
- `hydra-brute-force-output.png`
- `hydra-login-success.png`


### 2. Command Injection
- **Target**: `/vulnerabilities/exec/`
- **Payload**: `127.0.0.1; whoami`
- **Result**: Arbitrary OS commands executed on server.

**Screenshots**:
- `cmd-injection-form.png`
- `cmd-injection-output.png`
- `cmd-injection-output2.png`


### 3. File Upload (Remote Code Execution)
- **Target**: `/vulnerabilities/upload/`
- **Payload**: Malicious PHP shell disguised as `.jpg` with `.php.jpg` trick
- **Result**: Gained code execution via web shell.

**Screenshots**:
- `file-upload-page.png`
- `file-upload-success.png`
- `file-upload-shell-output.png`


### 4. SQL Injection
- **Target**: `/vulnerabilities/sqli/`
- **Payloads**:
  - `' OR 1=1-- -`
  - `' UNION SELECT 1, version()-- -`
- **Result**: Extracted database version and bypassed authentication.

**Screenshots**:
- `sql-injection-form.png`
- `sql-injection-result.png`
- `sql-injection-union.png`


### 5. Cross-Site Scripting (XSS)

#### ▸ Reflected XSS
- **Target**: `/vulnerabilities/xss_r/`
- **Payload**: `<script>alert('XSS')</script>`

**Screenshots**:
- `xss-reflected-form.png`
- `xss-reflected-alert.png`

#### ▸ Stored XSS
- **Target**: `/vulnerabilities/xss_s/`
- **Payload**: `<script>alert('XSS')</script>` stored in message/comment

**Screenshots**:
- `xss-stored-form.png`
- `xss-stored-popup.png`


## Notes

- All tests were conducted in a controlled lab setup.
- This project is strictly for educational and ethical hacking purposes.
- Never attempt these techniques on unauthorized systems.


## Screenshots Overview

You can find all relevant screenshots in the [`/screenshots`](./screenshots/) folder.


This project is intended for educational purposes only. All testing was performed in a controlled environment.


## Author
- **Mihir Kulkarni**
- **LinkedIn**: https://www.linkedin.com/in/mihir-kulkarni-973762227/

