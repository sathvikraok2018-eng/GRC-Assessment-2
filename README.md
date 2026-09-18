# GRC-Assessment-2

## PCI-DSS 4.0 Security and compliance assessments : D2C E-Commerce Platform

## Platform context and Cardholder Data Environment (CDE)

* Business format: D2C E-Commerce retail platform with cloud hosted payment integrations
* Primary target: Cardholder Data Environment (CDE), checkout web application, customer database, AWS infrastructure.
* Key and sensitive data handled:
  * Primary Account Number (PAN)
  * cardholder name and expiry dates
  * customer PII and transaction history
  * Sensitive authentication data 

## GAP ANALYSIS SUMMARY (PCI-DSS)

| Requirement ID | Current state (Baseline flow) | Desired state (Target control) | Priority |
| :--- | :--- | :--- | :--- |
| PCI 3.4.1 | PAN stored in clear text inside database temp logs during checkout failures | Render all PAN unreadable using strong cryptography (AES-256) | CRITICAL |
| *PCI 6.4.3* | Third-party payment page scripts run without integrity tracking (Magecart risk). | Deploy Content Security Policy (CSP) headers & Subresource Integrity (SRI) hashes. | *HIGH* |
| *PCI 8.3.6* | AWS cloud infrastructure access relies on single-factor passwords. | Mandate MFA/TOTP for all administrative access into the CDE. | *HIGH* |
| *PCI 10.4.1* | Payment app logs stored locally on web servers without central aggregation. | Deploy a centralized SIEM tool with immutable write-once log storage. | *MEDIUM* |
| *PCI 12.8.2* | Payment API vendors integrated without tracking annual PCI compliance certificates. | Establish a TPRM policy requiring annual AOC collection and risk reviews. | *MEDIUM* |
