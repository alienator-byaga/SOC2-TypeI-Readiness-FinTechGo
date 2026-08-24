# FinTech Go Inc. — SOC 2 Type I Gap Analysis Report

**Prepared by:** Aaliyan Qureshi  
**Assessment Date:** August 2026  
**Status:** Remediations Required Prior to Engagement  

---

## 1. Access Control & Identity Management (CC6.1, CC6.2)
* **Identified Gap:** 30 developers maintain persistent root-level access to the primary AWS production account. Multi-Factor Authentication (MFA) and Single Sign-On (SSO) are not strictly enforced.
* **Risk Severity:** Critical
* **Remediation Plan:**
  1. Secure AWS root credentials with a physical MFA hardware token.
  2. Implement AWS IAM Identity Center federated with Google Workspace SSO.
  3. Enforce WebAuthn / TOTP MFA account-wide.
  4. Restrict developer access using Role-Based Access Control (RBAC) based on Least Privilege.
* **Audit Evidence Required:** IAM Identity Center policy export, Google Workspace MFA enforcement status, AWS CloudTrail access logs.

---

## 2. Change Management & Software Deployment (CC8.1)
* **Identified Gap:** Code updates are deployed directly from developer laptops to live production EKS clusters using terminal commands (`kubectl apply`), bypassing code review, testing, and segregation of duties.
* **Risk Severity:** High
* **Remediation Plan:**
  1. Configure GitHub branch protection rules requiring at least 1 mandatory peer approval before merging to `main`.
  2. Implement a CI/CD pipeline (GitHub Actions) for automated unit testing and security scanning (SAST).
  3. Revoke direct developer access to production Kubernetes clusters; delegate deployment execution strictly to CI/CD service roles.
* **Audit Evidence Required:** GitHub branch protection settings screenshots, sample PR logs showing review/approval timestamps and automated test passes.

---

## 3. Third-Party Vendor Risk Management (CC9.2)
* **Identified Gap:** Core SaaS integrations (OpenAI API, FastAuth KYC, Twilio) were onboarded without formal security evaluations or Data Processing Agreements (DPAs) protecting customer PII/financial data.
* **Risk Severity:** High
* **Remediation Plan:**
  1. Establish a central Vendor Risk Inventory database.
  2. Perform annual vendor risk reviews and collect SOC 2 Type II / ISO 27001 certifications.
  3. Execute formal DPAs containing zero data-retention clauses with OpenAI and FastAuth.
* **Audit Evidence Required:** Populated Vendor Inventory Register, executed DPAs, archive of vendor SOC 2 reports.

---

## 4. Incident Response & Business Continuity (CC7.3, CC7.4)
* **Identified Gap:** PostgreSQL RDS database relies on ad-hoc manual snapshots with no defined Recovery Point Objective (RPO) or Recovery Time Objective (RTO). No central log monitoring or formal Incident Response Plan (IRP) exists.
* **Risk Severity:** Medium
* **Remediation Plan:**
  1. Enable AWS RDS Automated Backups (35-day Point-in-Time Recovery) and Multi-AZ failover.
  2. Document a formal Incident Response Plan defining severity metrics, commander roles, and escalation steps.
  3. Route CloudWatch logs to a SIEM/alerting system for anomaly detection.
* **Audit Evidence Required:** Documented IRP, annual tabletop simulation report, RDS configuration export, backup restoration verification logs.
