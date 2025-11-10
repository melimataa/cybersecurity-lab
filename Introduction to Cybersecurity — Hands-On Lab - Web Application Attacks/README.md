# Case Study:  Introduction to Cybersecurity — Hands-On Lab - Web Application Attacks 


## 🔍 Overview 
This repository documents a hands-on lab using Damn Vulnerable Web Application (DVWA) to practice and understand common web vulnerabilities. The goal is to learn how attacks work, their real-world impact, and how to mitigate them.

⚠️ Educational use only: all examples are sanitized and should be run in safe and local labs.

🔒 Reflects good cybersecurity practices and ethical responsibility.


---

## 🚀 How to run DVWA locally

Requirements:
* Docker
* Docker Compose (optional)
* Web browser

Steps:


### 1. Clone this repository:

```bash
git clone https://github.com/your_username/DVWA-HandsOn.git
```


### 2. Change into the project directory:

```bash
cd DVWA-HandsOn
```


### 3. Run DVWA with Docker:

```bash
docker run --rm -it -p 80:80 vulnerables/web-dvwa
```


Or using Docker Compose (example docker-compose.yml can be added to repo).


### 4. Open your browser to the DVWA instance and follow the Setup page to initialize the database.



---

## 🔎 Vulnerabilities covered (SANITIZED examples)

Note: all concrete exploit strings have been replaced with placeholders. Replace placeholders only inside a private, isolated lab.



### 🚨 1. SQL Injection

Sanitized placeholder:

```
<SQL_INJECTION_PAYLOAD_EXAMPLE>
```


🔸 Why it works:
User input concatenated into SQL queries without proper parameterization can change query logic and return or modify data.

🔸 Mitigations:
* Use prepared statements / parameterized queries
* Strict input validation and sanitization
* Apply least privilege to database accounts
* Store passwords with secure hashing (e.g., bcrypt)

![Description of image](G0N2cbt.png)

---

### 🚨 2. Directory Traversal (File Inclusion)

Sanitized placeholder:

```
<DIR_TRAVERSAL_PAYLOAD_EXAMPLE>
```

🔸 Why it works:
Building file paths from user input without normalization allows path-traversal sequences to access files outside the intended directory.

🔸 Mitigations:
* Normalize and validate file paths
* Use an allowlist of permitted files
* Place secrets outside the webroot
* Restrict file system permissions

---

### 🚨 3. CSRF (Cross-Site Request Forgery)

Sanitized (conceptual):

```
<CSRF_CONCEPT_EXAMPLE>
```

🔸 Why it works:
No verification that the request originates from the legitimate site or user — attacker tricks an authenticated browser into making state-changing requests.

🔸 Mitigations:
* Implement anti-CSRF tokens (synchronizer tokens)
* Validate Origin/Referer headers when possible
* Use same-site cookies and require POST for state changes

---

### 🚨 4. XSS Stored (Cross-Site Scripting — Stored)

Sanitized placeholder: 

```
<XSS_STORED_PAYLOAD_EXAMPLE>
```

🔸 Why it works:
User input stored and later rendered without escaping enables JavaScript execution in other users' browsers.

🔸 Mitigations:
* Sanitize and escape all user content before rendering (HTML encoding)
* Implement Content Security Policy (CSP)
* Mark cookies as HttpOnly to prevent JavaScript access

---

### 🚨 5. Blind SQL Injection (Optional)

Sanitized placeholder: 

```
<BLIND_SQLI_TECHNIQUE_EXAMPLE>
```

🔸 Notes:
Blind SQLi extracts data using side-channels (timing, boolean responses) when errors are not displayed. Use parameterized queries and avoid leaking DB behavior.

---

### 🚨 6. Command Injection (Optional)

Sanitized placeholder:

```
<COMMAND_INJECTION_PAYLOAD_EXAMPLE>
```

🔸 Why it works:
User input passed to OS command execution without sanitization enables command chaining and arbitrary execution.

🔸 Mitigations:
* Avoid invoking shell commands with user input
* Validate and sanitize inputs; use safe APIs
* Run processes with minimal privileges

---


## 💭 Final Reflection
* Confidentiality: Attacks like SQLi and Directory Traversal expose private data.
* Integrity: Attackers can alter or delete data.
* Availability: Exploits can cause downtime or degraded service.

## ✅ General best practices:
* Strict input validation and sanitization
* Secure server configuration and updated dependencies
* Principle of least privilege for services and databases
* Use security headers (CSP, HSTS, X-Frame-Options, etc.)
* Apply proper authentication, session management, and token protections

---

## 🔒 payloads_sanitized.md (embedded)

This section provides safe, educational guidance about each technique and how to work with placeholders instead of real exploit strings. If you prefer, this content can be split into a separate file (payloads_sanitized.md) — both options are acceptable.

### Purpose

This section contains **sanitized** example payloads and step-by-step explanations for each technique covered in the hands‑on lab. **Never** copy these verbatim into a public environment. Use real payloads **only** inside an isolated local lab (Docker/VM/private network).

### How to use these placeholders

* Replace placeholders like ```<SQL_INJECTION_PAYLOAD_EXAMPLE>``` only within a local DVWA instance or other isolated lab.
* Do not commit exploit strings or sensitive screenshots to public repos. Use ```[REDACTED]``` or placeholders in images and text.
* If you accidentally expose sensitive content, follow the repo cleanup steps (make repo private, remove files from HEAD, re-write history if necessary, rotate credentials).

### Safe testing guidance (summary)

* Start DVWA locally in Docker: ```docker run --rm -it -p 80:80 vulnerables/web-dvwa```
* Use DVWA only in a private/local network.
* Replace placeholders **only** inside your lab's requests or UI.
* Log results locally; do not upload raw exploit strings to public repos.

### Educational / legal / ethical note

Performing attacks against systems you do not own or have explicit permission to test is illegal in many jurisdictions. This material is for learning in controlled environments only. Always obtain explicit authorization before performing any security testing on systems you do not own.

### Quick actions & tips for maintainers

* Keep this repo private until you are comfortable with the public content.
* Redact any screenshots (blur or overlay ```[REDACTED]``` / placeholders) before committing.
* If you need to remove a file from the repository history, use BFG or git-filter-repo.
* Add a short blurb for recruiters explaining that the repo is sanitized and available upon request.



