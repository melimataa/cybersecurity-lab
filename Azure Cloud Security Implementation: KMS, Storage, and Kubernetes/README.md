# Azure Cloud Security Implementation: KMS, Storage, and Kubernetes

This project documents the **security configuration in Azure** for an IaaS environment, including:

- Key management with KMS
- Secure Storage Account setup
- Encrypted AKS (Kubernetes) cluster creation

## Objective
To protect company data, secure communications, and maintain a secure Kubernetes environment.

## Security Architecture
1. **KMS Key:** Master key for encrypting data.
2. **Storage Account:** Secure configuration including:
   - Secure transfer (HTTPS)
   - TLS 1.2
   - Soft delete and versioning for blobs
   - Encryption with CMK (Customer Managed Key)
3. **AKS Cluster:** Secure Kubernetes cluster connected to the encrypted Storage Account.

![Architecture Diagram]()

## How to Use
1. Create a KMS key in Azure.
2. Create a Storage Account with the recommended security settings.
3. Create an AKS cluster and connect it to the Storage Account.

![Security Architecture](https://i.imgur.com/DKM5U5w.png)
