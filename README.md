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
