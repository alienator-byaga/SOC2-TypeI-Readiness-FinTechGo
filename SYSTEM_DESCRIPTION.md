# FinTech Go Inc. — System Description & Audit Scope

## 1. Company Overview
FinTech Go Inc. is a financial technology startup operating a mobile payment application that facilitates peer-to-peer (P2P) transfers and merchant payments. 

* **Headquarters:** San Francisco, CA (Fully Remote)
* **Team Size:** 45 Employees (30 Engineering, 5 Product, 10 Operations)
* **Target Framework:** AICPA SOC 2 Type I — Security Criteria (Trust Services Criteria)

---

## 2. Infrastructure & Technical Stack
The operational environment supporting the FinTech Go payment processing platform comprises the following cloud-native components:

* **Cloud Infrastructure:** Amazon Web Services (AWS)
  * Elastic Kubernetes Service (EKS) for application microservices
  * PostgreSQL Amazon RDS for primary relational database storage
  * Amazon Simple Storage Service (S3) for media and logs
* **Code Repository & Version Control:** GitHub Organization
* **Identity & Access Management:** Google Workspace SSO, AWS IAM Identity Center
* **Collaboration & Operations:** Slack, Google Workspace

---

## 3. Scope of the Assessment
The SOC 2 Type I readiness assessment evaluates the design suitability of controls across the following Trust Services Criteria (TSC) domains:

| Domain | Focus Area | Applicable Standard |
| :--- | :--- | :--- |
| **CC6.1 / CC6.2** | Logical Access Controls & Identity Management | Security |
| **CC7.3 / CC7.4** | Incident Response, Backup & Business Continuity | Security & Availability |
| **CC8.1** | Change Management & Infrastructure Deployment | Security |
| **CC9.2** | Third-Party Vendor Risk Management | Security & Confidentiality |
