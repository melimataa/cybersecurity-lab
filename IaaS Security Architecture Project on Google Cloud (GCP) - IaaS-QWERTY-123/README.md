# IaaS Security Architecture Project on Google Cloud (GCP) - IaaS-QWERTY-123

This repository documents the design and implementation of a robust and scalable security architecture in GCP, following an Infrastructure as a Service (IaaS) model.  
The goal is to protect business resources, secure communications, and establish a solid identity and access management framework.

---

## 📡 Network and Access Architecture (Perimeter Layer)

This section describes how clients/users securely access the services.

### Entry Point
- **Main Function:** The initial gateway for client traffic (employees, partners, etc.)
- **Relevant GCP Services:** Cloud VPN, Endpoint Security, Identity-Aware Proxy (IAP)

### Network Perimeter
- **Main Function:** Defines and enforces edge security policies for the network
- **Relevant GCP Services:** VPC Gateway, Load Balancer, Cloud WAF/CDN

### Access to Main Environment
- **Main Function:** Secure connection from the perimeter network to the main VPC
- **Relevant GCP Services:** Cloud Armor, IPsec/TLS

### IP Address: 192.168.1.25
- **Main Function:** Representative IP of a key resource or access point
- **Relevant GCP Services:** Indicates a specific resource

---

## 🔐 Core Security and Governance Layers

1. **Client Identification & Authentication (IAM)**
   - Security Keys / Certificates: Strong authentication
   - MFA: Mandatory multi-factor authentication
   - Identity Service: Centralized identity management

2. **Task Management**
   - Deployment Manager: Infrastructure as Code (IaC)
   - IAM Management Service: Principle of least privilege

3. **Monitoring & Logging**
   - Cloud Audit Logs: Activity logging
   - Security Health Analytics: Configuration scanning
   - Cloud Profiles / Policies: Compliance standards
   - Stackdriver: Logs, metrics, and tracing

---

## 🖥️ Compute and Network Architecture (VPC & Zones)

**Public Network (Public Subnet - US-West-x and US-Central-x)**
- US-West-x (Application): VMs, load balancers, routing rules (IP 192.168.2.x)
- US-Central-x (Process): Proxies and jump-hosts (IP 192.168.3.x)

**Private Network (Private Subnet - US-West-x)**
- IaaS Infrastructure: Critical VMs (IP 192.168.4.x)
- Storage & Data: Cloud SQL, GCS Bucket
- Controlled Access: Firewall and VPC Peering

---

## 📊 Diagrams & Visual Resources

![Architecture Diagram](https://i.imgur.com/o5m3uFQ.png)

---

## ✅ Conclusion

This project follows cloud security best practices, implementing defense in depth, separation of duties, and full observability using native GCP tools.
