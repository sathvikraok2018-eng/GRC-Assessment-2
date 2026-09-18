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

 ------

## GAP ANALYSIS SUMMARY (PCI-DSS)

| Requirement ID | Current state (Baseline flow) | Desired state (Target control) | Priority |
| :--- | :--- | :--- | :--- |
| PCI 3.4.1 | PAN stored in clear text inside database temp logs during checkout failures | Render all PAN unreadable using strong cryptography (AES-256) | CRITICAL |
| *PCI 6.4.3* | Third-party payment page scripts run without integrity tracking (Magecart risk). | Deploy Content Security Policy (CSP) headers & Subresource Integrity (SRI) hashes. | *HIGH* |
| *PCI 8.3.6* | AWS cloud infrastructure access relies on single-factor passwords. | Mandate MFA/TOTP for all administrative access into the CDE. | *HIGH* |
| *PCI 10.4.1* | Payment app logs stored locally on web servers without central aggregation. | Deploy a centralized SIEM tool with immutable write-once log storage. | *MEDIUM* |
| *PCI 12.8.2* | Payment API vendors integrated without tracking annual PCI compliance certificates. | Establish a TPRM policy requiring annual AOC collection and risk reviews. | *MEDIUM* |

------



## 📋 Third-Party Risk Management (TPRM) Vendor Questionnaire

	
* Instructions for Vendor:
* Complete this security assessment regarding your third-party integration with our Cardholder Data Environment (CDE). All responses must be verified by your Chief Information Security Officer (CISO) or designated security lead prior to contract execution or renewal.

### Section A: Data Governance & Encryption

| # | Security Question | Response Format | Vendor Response & Details |
| :---: | :--- | :---: | :--- |
| *A.1* | do you store, process, or transmit Primary Account Numbers (PAN) or Sensitive Authentication Data (SAD) on our behalf? | ⁠ [Yes / No] ⁠ | *Response:* <br>If Yes, specify exact data fields: |
| *A.2* | Is all data in transit encrypted using TLS 1.3, and is all cardholder dta at rest encrypted using AES-256 or equivalent? | ⁠ [Yes / No] ⁠ | *Response:* <br>Provide cryptographic protocols used: |
| *A.3* | Can you confirm that Sensitive Authentication Data (CVV/CVC codes) is imediately purged after transaction authorization and never stored under any circumstances? | ⁠ [Yes / No] ⁠ | *Response:* |

---

### Section B: Access Control & Network Security

| # | Security Question | Response Format | Vendor Response & Details |
| :---: | :--- | :---: | :--- |
| *B.1* | Is Multi-Factor Authentication (MFA) mandatory for all vendor personnel accessing systems that connect to our API or data strams? | ⁠ [Yes / No] ⁠ | *Response:* |
| *B.2* | Do you enforce the Principle of Least Privilege and Role-Based Access Contol (RBAC) for vendor API tokens and service accounts? | ⁠ [Yes / No] ⁠ | *Response:* |
| *B.3* | How frequently are service account API keys rotated, and what is your process for imediate revocation during a credential leak? | ⁠ [Text] ⁠ | *Response Details:* |

---

### Section C: Vulnerability Management & 

| # | Security Question | Response Format | Vendor Response & Details |
| :---: | :--- | :---: | :--- |
| *C.1* | Do you conduct annual external penetration testing and quarterly vulnerability scans on all infrastructure supporting our integration? | ⁠ [Yes / No] ⁠ | *Response:* <br>Attach Executive Summary of most recent test. |
| *C.2* | What is your contractual Service Level Agreement (SLA) for notifying us in the event of a confirmed or suspected security breach? | ⁠ [Text] ⁠ | *Response Details:* (Must be ≤ 24 hours) |

---






