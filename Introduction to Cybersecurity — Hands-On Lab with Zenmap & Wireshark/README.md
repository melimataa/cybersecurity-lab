# Case Study: Introduction to Cybersecurity — Hands-On Lab with Zenmap & Wireshark

## 🔍 Overview
This hands-on project explores the fundamentals of **network auditing and vulnerability detection** using two essential tools: **Zenmap (Nmap GUI)** and **Wireshark**.  
The goal is to understand how attackers can perform reconnaissance through network scans and how encryption (HTTPS) protects data transmitted over the web.

---

## 🧰 Tools Used
- 🧭 **Zenmap (Nmap GUI)** – Network scanning and host discovery  
- 🕵️ **Wireshark** – Packet capture and traffic analysis  
- 💻 **Virtual Machine Environment** – Simulated subnet for testing  

---

## ⚙️ Zenmap Section

### 🧩 Exercise 1: Network Connection & Discovery
- VM: `ajimeneze-vm`
- Private IP: `10.0.1.9`

---

### 🔎 Exercise 2: Quick Port Scan
**Hosts detected:** 7  
`10.0.1.1 (Gateway), 10.0.1.4 – 10.0.1.9`

**Open ports and services:**

| Port | Service | Description |
|------|----------|-------------|
| 80 | HTTP | Web server |
| 3389 | RDP | Remote Desktop |
| 135 | MSRPC | Windows internal communication |
| 139 | NetBIOS | Legacy file sharing |
| 445 | SMB | Modern file sharing |
| 5301 / 5357 | WSDAPI | Device discovery |

---

### 🧠 Exercise 3: OS Detection Scan
Zenmap identified multiple systems running:
- **Windows Server 2012 R2 (85%)**
- **Windows Server 2016 (85%)**
- **Windows Server 2022 (89%)**

---

### 🚨 Exercise 4: Vulnerability Scan
Detected potential vulnerabilities:

| Vulnerability | Description | Risk |
|----------------|--------------|------|
| Slowloris DoS (CVE-2007-6750) | HTTP Denial of Service on host 10.0.1.6 | 🔴 High |
| RDP (3389) | Possible brute-force or unauthorized access | 🟠 Medium |
| WinRM (5985) | Potential credential abuse | 🟠 Medium |
| SMB/NetBIOS (135/139/445) | Lateral movement risk | 🔴 Critical |
| HTTP (80) | Exposed web surface | 🟡 Low |

---

## 🌐 Wireshark Section

### 🧾 Step 1: Capture HTTP Traffic
Captured HTTP packets showing credentials transmitted **in plaintext**.

### 💬 Step 2: Why credentials were visible
HTTP lacks encryption — without **TLS/SSL**, all data travels unprotected.

### 🔒 Step 3: Capture HTTPS Traffic
Captured encrypted packets labeled as “Application Data.”

### 🔐 Step 4: Why credentials are now protected
Using **HTTPS** activates the **TLS protocol**, ensuring:
- 🔸 Data encryption (confidentiality)  
- 🔸 Message integrity (no tampering)  
- 🔸 Authentication via digital certificates  

---

## 🎯 Bonus Challenge
Students attempted unauthorized **RDP/SSH remote access** to the instructor’s VM using a shared default password.  
Some succeeded, demonstrating the importance of **strong and unique credentials** in network environments.

---

## 💭 Reflection

**1. Why are port and vulnerability scans important?**  
They help identify weaknesses such as misconfigurations or outdated software. Without them, attackers can exploit vulnerabilities, compromise sensitive data, and cause business disruptions.

**2. Why use HTTPS instead of HTTP?**  
HTTPS encrypts data, protecting credentials and sensitive information during transmission — especially on public networks — although it doesn’t eliminate all external threats.

---

## 🧩 Learning Outcomes
✔️ Performed network scanning and host discovery using Zenmap  
✔️ Detected open ports, services, and vulnerabilities  
✔️ Captured and analyzed HTTP/HTTPS traffic with Wireshark  
✔️ Understood the value of encryption and secure configurations  
