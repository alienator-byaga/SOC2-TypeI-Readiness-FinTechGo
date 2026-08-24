# SOC 2 Type I Readiness & Gap Analysis — FinTech Go Inc.

This repository contains a complete, simulated **SOC 2 Type I Readiness Assessment** conducted for **FinTech Go Inc.**, a fictional 45-person B2B/P2P fintech startup preparing for enterprise audit compliance.

The goal of this project is to demonstrate practical Governance, Risk, and Compliance (GRC) methodologies, mapping technical infrastructure vulnerabilities to AICPA Trust Services Criteria (TSC) and defining actionable remediation plans.

---

## 📄 Repository Structure

* **`SYSTEM_DESCRIPTION.md`**: Outlines FinTech Go’s system architecture, technical stack, organizational boundaries, and audit scope.
* **`GAP_ANALYSIS.md`**: Detailed breakdown of control deficiencies across Access Control (CC6.1/CC6.2), Change Management (CC8.1), Vendor Risk (CC9.2), and Incident Response (CC7.3/CC7.4), including required audit evidence and remediation steps.
* **`FinTech_Go_SOC2_Gap_Analysis_Report.pdf`**: Executive-ready PDF deliverable summarizing findings, risk severities, and remediation timelines.

---

## 🎯 Key Framework Controls Assessed
* **CC6.1 / CC6.2 (Logical Access Controls):** Transitioning persistent AWS root access to SSO/MFA and Role-Based Access Control (RBAC).
* **CC8.1 (Change Management):** Enforcing GitHub branch protections, peer reviews, CI/CD automated testing, and Segregation of Duties (SoD).
* **CC9.2 (Vendor Risk Management):** Establishing vendor risk tiering, inventory tracking, and Data Processing Agreements (DPAs) for third-party AI/SaaS sub-processors.
* **CC7.3 / CC7.4 (Incident Response & Continuity):** Implementing automated RDS Multi-AZ backups, RPO/RTO metrics, SIEM logging, and formal IRPs.
