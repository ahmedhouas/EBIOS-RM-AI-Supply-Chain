# Risk Sources and Target Objectives (SR/OV)

**Section 1:** Threat Sources Identification

**Section 2:** Initial SR/OV inventory

## Objective and Scope

This document details the list of threat sources (SR) and their objectives (OV). It relies on the information provided in Workshop 1: Essential Assets and Supporting Assets, the list of Feared Events (ER) from the consolidated report, and the list of Dangerous Events (ED) which are retained as supporting information for Workshop 2. The following steps (evaluation, selection and mapping) will rely on the SR/OV pairs identified.


---

## 1. Threat Sources Identification

The list of threat sources is split between internal and external with a link to the Supporting Assets identified in Workshop 1 they are most likely to affect.

### 1.1 Internal sources

| ID | Category | Source | Description | Assets |
|---|---|---|---|---|
| SR1 | Internal | Malicious employee | A malicious employee has access to the system and will steal, alter or leak company data, orders and supplier information. | Operational database, data lake, dashboards, ERP/WMS/TMS |
| SR2 | Internal | Malicious system administrator | The system administrator will misuse their increased access to systems and accounts. They may be able to bypass approvals, change configuration and delete/alter logs. | Privileged users, logging system, server & cloud infrastructure, ERP/WMS/TMS |
| SR3 | Internal | Malicious data scientist / ML engineer | Someone may abuse their access to the models and training data to steal or tamper with them. | Model registry, training pipeline, AI services, data lake |
| SR4 | Internal | Inattentive employee | Warehouse, procurement or logistics employees can cause damage unintentionally. This may include entering incorrect data, misconfigured systems, leaking credentials and phishing. | Dashboards, IoT/barcode terminals, integration service, sales platform |

### 1.2 External sources

| ID | Category | Source | Description | Related supporting assets |
|---|---|---|---|---|
| SR5 | External | Competitor | A competitor wanting to gain an advantage by stealing forecasts, supplier terms, customer data and trained models. | Data lake, AI models & training data, operational database |
| SR6 | External | Organised cyber criminals | A financially motivated group who will use ransomware, data theft and fraud against exposed systems and users. | Server, cloud & network infrastructure, sales platform & order API, ERP |
| SR7 | External | Fraudulent / compromised supplier / carrier | A supplier/carrier who will manipulate data, produce fake invoices and delivery events, or have compromised systems which are used as an entry point. | Supplier portals, carrier tracking, integration service, ERP |
| SR8 | External | Third-party AI / Cloud provider | A third party who provides the infrastructure or models, libraries and datasets. This is considered a threat source due to being a weak link in the supply chain. If there is a breach, compromised component or failure, this can impact the organisation (see ED-T1, ED-IA1 & ED-IA2). This is unintentional. | Server, cloud & network infrastructure, AI services, model registry & pipeline |
| SR9 | External | State-sponsored | An individual/group with significant resources wanting to cause disruption or espionage to the supply chain. There was no direct Dangerous Event in Workshop 1 relating to this, so the link to the study is less strong (see notes). | Server & network infrastructure, ERP/WMS/TMS, integration service |
| SR10 | External | Adversarial AI attacker | An individual targeting the AI layer (Chapter 6 ISO/IEC 27090). This could involve poisoning input data, creating inputs to trick models (evasion), prompting malicious instructions (prompt injection), or querying exposed services to extract the model. | IoT sensors, external data sources, AI services, UIs, sales platform & order API |
| SR11 | External | Hacktivist | An individual with a motive to cause disruption or embarrassment to the organisation. They will mainly cause disruption via denial of service (ED-M3) or defacing exposed services. This is cited as an example threat source in the conclusion of Workshop 1. | Sales platform & order API, server, cloud & network infrastructure, dashboards |

---

## 2. Initial SR/OV Inventory

Each pair links a risk source (SR) to a target objective (OV), to a Feared Event (ER) from the consolidated Workshop 1 report, and to the Dangerous Event (ED) that describes how it can happen. Severity is derived from the Workshop 1 classification of the affected Essential Asset (see the scale below).

**Severity scale (derived from Workshop 1 classes)**

| Class of the affected property | Severity |
| :--- | :--- |
| C1, D1 | 1 (Minor) |
| C2, D2, I1 | 2 (Moderate) |
| C3, D3, I2 | 3 (Major) |
| D4 | 4 (Critical) |

| Pair ID | Risk source | Target objective (OV) | Feared event (Workshop 1) | Dangerous event (Workshop 1) | Severity |
| :--- | :--- | :--- | :--- | :--- | :--- |
| SR1-OV1 | SR1 Malicious employee | Steal or disclose customers' personal data | ER3.3 Unauthorized disclosure of customers' personal data (EA3, C3) | ED-M4, ED-M6 | 3 |
| SR1-OV2 | SR1 Malicious employee | Alter customer-order information for fraud or sabotage | ER3.5 Unauthorized modification of customer-order information (EA3, I2) | ED-M6 | 3 |
| SR2-OV3 | SR2 Malicious system administrator | Alter or erase logs to hide malicious activity | ER8.1 Unauthorized modification of decision and activity logs (EA8, I2) | ED-M7 | 3 |
| SR2-OV4 | SR2 Malicious system administrator | Bypass human validation of high-value orders | ER2.2 Circumvention of human validation for high-value orders (EA2, I2) | ED-M6 | 3 |
| SR3-OV5 | SR3 Malicious data scientist / ML engineer | Steal the proprietary AI models | ER7.2 Unauthorized extraction or disclosure of proprietary AI models (EA7, C3) | ED-IA6 | 3 |
| SR3-OV6 | SR3 Malicious data scientist / ML engineer | Tamper with models or training data | ER7.1 Biased or poisoned AI models (EA7, I2) | ED-IA2, ED-IA1 | 3 |
| SR4-OV7 | SR4 Careless employee | Corrupt business data by mistake (wrong entry, misconfiguration) | ER6.1 Unauthorized or erroneous corruption of business and historical data (EA6, I2) | ED-H1 | 3 |
| SR5-OV8 | SR5 Competitor | Obtain historical sales and strategic data | ER1.3 Disclosure of historical sales and strategic data (EA1, C2) | ED-M4 | 2 |
| SR6-OV9 | SR6 Organized cybercriminal group | Destroy or encrypt historical data to demand a ransom | ER6.4 Irrecoverable loss of historical business data (EA6, D3) | ED-M1 | 3 |
| SR7-OV10 | SR7 Fraudulent or compromised supplier / carrier | Manipulate supplier and delivery data to distort risk assessment | ER5.1 Inaccurate supplier risk assessment (EA5, I1) | ED-M5 | 2 |
| SR8-OV11 | SR8 Third-party AI / cloud provider | Failure or compromise of hosted data services | ER6.3 Unavailability of the data warehouse (EA6, D3) | ED-T1 | 3 |
| SR9-OV12 | SR9 State-sponsored actor | Espionage on proprietary AI models | ER7.2 Unauthorized extraction or disclosure of proprietary AI models (EA7, C3) | ED-IA6 | 3 |
| SR10-OV13 | SR10 External adversarial AI attacker | Poison input data to bias the models | ER7.1 Biased or poisoned AI models (EA7, I2) | ED-IA1 | 3 |
| SR10-OV14 | SR10 External adversarial AI attacker | Craft inputs that evade anomaly detection | ER4.3 Evasion or circumvention of anomaly-detection controls (EA4, I2) | ED-IA3 | 3 |
| SR10-OV15 | SR10 External adversarial AI attacker | Inject malicious instructions to manipulate AI recommendations | ER2.1 Incorrect replenishment recommendations (EA2, I2) | ED-IA7 | 3 |
| SR11-OV16 | SR11 Hacktivist | Take the sales platform and order API offline (denial of service) | ER3.2 Unavailability of the sales platform or order API (EA3, D4) | ED-M3 | 4 |

---

## Notes and assumptions

- Sources SR1 to SR4 are internal; SR5 to SR11 are external.
- Administrators and data scientists are listed as separate internal sources (SR2, SR3) because their access and targets differ: administrators act on systems, accounts and logs; data scientists act on models and training data.
- SR7 groups suppliers and carriers because they act in the same way (manipulated or compromised data feeds).
- SR9 has no direct Dangerous Event in Workshop 1. It can be kept for completeness or dropped in the scoring step if its relevance is low.
- SR11 was added because the Workshop 1 conclusion lists hacktivists as an example risk source.
- ISO/IEC 27090, Chapter 6 attack types covered: data poisoning (ED-IA1, ED-IA2), evasion (ED-IA3), model theft (ED-IA6) and prompt injection (ED-IA7). Membership inference (ED-IA4), model inversion (ED-IA5) and output injection (ED-IA8) can be added if needed.
- Pairs use the Feared Events of the consolidated Workshop 1 report (draft final report), which is the latest version.
- Severity is not defined in Workshop 1. It is derived from the class (C, I, D) of the affected Essential Asset using the scale in section 2. This is a project assumption to be confirmed.
- ER7.4 (undetected model drift) is not used because Workshop 1 marks its CIA class as "To be validated".
