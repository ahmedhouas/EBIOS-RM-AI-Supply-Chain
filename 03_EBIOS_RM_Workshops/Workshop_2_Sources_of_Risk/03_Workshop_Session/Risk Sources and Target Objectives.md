# Risk Sources and Target Objectives (SR/OV)

**Section 1:** Initial SR/OV Inventory

**Section 2:** Coverage Analysis of Workshop 1 Feared Events

**Section 3:** Assumptions and Notes

## Objective and Scope

This document details the list of risk sources (SR) and their target objectives (OV). It relies on the information provided in Workshop 1: Essential Assets and Supporting Assets, the 31 Feared Events (ER) of the consolidated report, and the Dangerous Events (ED) which are retained as supporting information for Workshop 2. The SR/OV pairs are built by cross-referencing the Workshop 1 Feared Events with the internal and external risk sources. The following steps (evaluation, selection and mapping) rely on the SR/OV pairs identified here.

---

## 1. Initial SR/OV Inventory

### 1.1 Risk Sources Identification

The list of risk sources is split between internal and external, with a link to the Supporting Assets identified in Workshop 1 that they are most likely to affect.

#### Internal sources

| ID | Category | Source | Description | Assets |
|---|---|---|---|---|
| SR1 | Internal | Malicious employee | A malicious employee has access to the system and will steal, alter or leak company data, orders and supplier information. | Operational database, data lake, dashboards, ERP/WMS/TMS |
| SR2 | Internal | Malicious system administrator | The system administrator will misuse their increased access to systems and accounts. They may be able to bypass approvals, change configuration and delete/alter logs. | Privileged users, logging system, server & cloud infrastructure, ERP/WMS/TMS |
| SR3 | Internal | Malicious data scientist / ML engineer | Someone may abuse their access to the models and training data to steal or tamper with them. | Model registry, training pipeline, AI services, data lake |
| SR4 | Internal | Inattentive employee | Warehouse, procurement or logistics employees can cause damage unintentionally. This may include entering incorrect data, misconfigured systems, leaking credentials and phishing. | Dashboards, IoT/barcode terminals, integration service, sales platform |

#### External sources

| ID | Category | Source | Description | Related supporting assets |
|---|---|---|---|---|
| SR5 | External | Competitor | A competitor wanting to gain an advantage by stealing forecasts, supplier terms, customer data and trained models. | Data lake, AI models & training data, operational database |
| SR6 | External | Organised cyber criminals | A financially motivated group who will use ransomware, data theft and fraud against exposed systems and users. | Server, cloud & network infrastructure, sales platform & order API, ERP |
| SR7 | External | Fraudulent / compromised supplier / carrier | A supplier/carrier who will manipulate data, produce fake invoices and delivery events, or have compromised systems which are used as an entry point. | Supplier portals, carrier tracking, integration service, ERP |
| SR8 | External | Third-party AI / Cloud provider | A third party who provides the infrastructure or models, libraries and datasets. This is considered a risk source due to being a weak link in the supply chain. If there is a breach, compromised component or failure, this can impact the organisation (see ED-T1, ED-IA1 & ED-IA2). This is unintentional. | Server, cloud & network infrastructure, AI services, model registry & pipeline |
| SR9 | External | State-sponsored | An individual/group with significant resources wanting to cause disruption or espionage to the supply chain. There was no direct Dangerous Event in Workshop 1 relating to this, so the link to the study is less strong (see notes). | Server & network infrastructure, ERP/WMS/TMS, integration service |
| SR10 | External | Adversarial AI attacker | An individual targeting the AI layer (Chapter 6 ISO/IEC 27090). This could involve poisoning input data, creating inputs to trick models (evasion), prompting malicious instructions (prompt injection), or querying exposed services to extract the model. | IoT sensors, external data sources, AI services, UIs, sales platform & order API |
| SR11 | External | Hacktivist | An individual with a motive to cause disruption or embarrassment to the organisation. They will mainly cause disruption via denial of service (ED-M3) or defacing exposed services. This is cited as an example risk source in the conclusion of Workshop 1. | Sales platform & order API, server, cloud & network infrastructure, dashboards |

### 1.2 Severity scale

Severity is derived from the Workshop 1 classification of the Essential Asset affected by the Feared Event, using the class of the property concerned (C for confidentiality, I for integrity, D for availability).

| Class of the affected property | Severity |
| :--- | :--- |
| C1, D1 | 1 (Minor) |
| C2, D2, I1 | 2 (Moderate) |
| C3, D3, I2 | 3 (Major) |
| D4 | 4 (Critical) |

### 1.3 SR/OV pairs

The pairs are grouped by risk source, in the format of the reference table (`Atelier2.PNG`): risk source, feared event, description and severity. Each description starts with the target objective (OV) of the pair and ends with the Dangerous Event (ED) of Workshop 1 that describes how it can happen. A single source may target several Feared Events, and several sources may target the same Feared Event.

| Risk source | Feared event | Description | Severity |
| :--- | :--- | :--- | :---: |
| **SR1 - Malicious employee** (Internal, malicious) | ER3.3 Unauthorized disclosure of customers' personal data (EA3, C3) | **Objective (SR1-OV1):** Steal or disclose customers' personal data. An employee with normal access copies or leaks customer personal data. **ED:** ED-M4, ED-M6. | 3 |
|  | ER3.5 Unauthorized modification of customer-order information (EA3, I2) | **Objective (SR1-OV2):** Alter customer-order information for fraud or sabotage. An employee changes order records to commit fraud or disrupt fulfilment. **ED:** ED-M6. | 3 |
| **SR2 - Malicious system administrator** (Internal, malicious) | ER8.1 Unauthorized modification of decision and activity logs (EA8, I2) | **Objective (SR2-OV3):** Alter or erase logs to hide malicious activity. An administrator erases or alters logs so that malicious actions cannot be traced. **ED:** ED-M7. | 3 |
|  | ER2.2 Circumvention of human validation for high-value orders (EA2, I2) | **Objective (SR2-OV4):** Bypass human validation of high-value orders. An administrator disables or bypasses approval rules so large orders pass without human review. **ED:** ED-M6. | 3 |
|  | ER2.4 Unauthorized modification of safety-stock requirements or thresholds (EA2, I2) | **Objective (SR2-OV21):** Change safety-stock thresholds without authorisation. An administrator changes safety-stock thresholds, causing stockouts or excess stock. **ED:** ED-M6. | 3 |
|  | ER4.1 Failure to identify abnormal or suspicious activity (false negatives) (EA4, I2) | **Objective (SR2-OV25):** Disable or weaken anomaly detection to hide fraud. An administrator disables or weakens detection rules so that suspicious activity goes unflagged. **ED:** ED-M6. | 3 |
| **SR3 - Malicious data scientist / ML engineer** (Internal, malicious) | ER7.2 Unauthorized extraction or disclosure of proprietary AI models (EA7, C3) | **Objective (SR3-OV5):** Steal the proprietary AI models. A data scientist copies the trained models out of the registry for personal or third-party gain. **ED:** ED-IA6. | 3 |
|  | ER7.1 Biased or poisoned AI models (EA7, I2) | **Objective (SR3-OV6):** Tamper with models or training data. A data scientist alters models or training data. Unregistered changes also make the model version unidentifiable (see ER1.4). **ED:** ED-IA2, ED-IA1. | 3 |
| **SR4 - Inattentive employee** (Internal, non-malicious) | ER6.1 Unauthorized or erroneous corruption of business and historical data (EA6, I2) | **Objective (SR4-OV7):** Corrupt business data by mistake (wrong entry, misconfiguration). An employee enters wrong data or misconfigures a system, and the error spreads into analyses and forecasts. **ED:** ED-H1. | 3 |
|  | ER1.1 Inaccurate or biased demand forecasts (EA1, I2) | **Objective (SR4-OV18):** Mislabel training data by mistake. An employee labels training data incorrectly, which biases the forecasting model. **ED:** ED-H5. | 3 |
|  | ER2.4 Unauthorized modification of safety-stock requirements or thresholds (EA2, I2) | **Objective (SR4-OV22):** Set safety-stock thresholds or permissions wrongly by mistake. An employee configures thresholds or access permissions incorrectly. **ED:** ED-H2. | 3 |
|  | ER4.2 Excessive false-positive alerts (EA4, I2) | **Objective (SR4-OV26):** Set alert thresholds wrongly by mistake. An employee sets alert thresholds incorrectly and triggers excessive false-positive alerts. **ED:** ED-H2. | 3 |
|  | ER8.2 Failure to record user overrides and their reasons (EA8, I2) | **Objective (SR4-OV31):** Skip human-validation procedures by mistake. An employee skips validation steps, so overrides and their reasons are not recorded. **ED:** ED-H4. | 3 |
|  | ER8.4 Loss or unavailability of decision and activity logs (EA8, D2) | **Objective (SR4-OV33):** Delete logs or data by mistake. An employee deletes logs or data by mistake, so decisions cannot be reviewed. **ED:** ED-H3. | 2 |
| **SR5 - Competitor** (External, malicious) | ER1.3 Disclosure of historical sales and strategic data (EA1, C2) | **Objective (SR5-OV8):** Obtain historical sales and strategic data. A competitor extracts historical sales and strategic data to gain a commercial advantage. **ED:** ED-M4. | 2 |
|  | ER5.3 Disclosure of supplier contracts and commercial conditions (EA5, C2) | **Objective (SR5-OV28):** Obtain supplier contracts and commercial conditions. A competitor obtains supplier contracts to weaken the organisation's negotiating position. **ED:** ED-M4. | 2 |
| **SR6 - Organised cyber criminals** (External, malicious) | ER6.4 Irrecoverable loss of historical business data (EA6, D3) | **Objective (SR6-OV9):** Destroy or encrypt historical data to demand a ransom. Criminals encrypt or destroy historical data and demand a ransom, leaving no usable history. **ED:** ED-M1. | 3 |
|  | ER2.3 Unavailability of the inventory optimization service (EA2, D4) | **Objective (SR6-OV20):** Encrypt or disable replenishment systems with ransomware. Ransomware encrypts the ERP and optimisation systems, halting replenishment decisions. **ED:** ED-M1. | 4 |
|  | ER3.1 Loss or unavailability of customer-order records (EA3, D4) | **Objective (SR6-OV23):** Encrypt or destroy customer-order records with ransomware. Ransomware encrypts or destroys customer-order records, so orders cannot be processed. **ED:** ED-M1. | 4 |
|  | ER6.2 Unauthorized disclosure of customer or supplier data (EA6, C3) | **Objective (SR6-OV29):** Steal customer or supplier data for sale or extortion. Criminals exfiltrate customer or supplier data to sell it or extort the organisation. **ED:** ED-M4. | 3 |
|  | ER8.3 Unauthorized access to logs (EA8, C2) | **Objective (SR6-OV32):** Phish privileged users to read sensitive logs. Criminals phish privileged users to gain access to operational and decision logs. **ED:** ED-M2. | 2 |
| **SR7 - Fraudulent / compromised supplier / carrier** (External, malicious) | ER5.1 Inaccurate supplier risk assessment (EA5, I1) | **Objective (SR7-OV10):** Manipulate supplier and delivery data to distort risk assessment. A compromised supplier feeds false data, which distorts the supplier risk assessment. **ED:** ED-M5. | 2 |
|  | ER3.4 Failure to deliver orders within the expected timeframe (EA3, D4) | **Objective (SR7-OV24):** Falsify or block delivery events to delay deliveries. A compromised carrier falsifies or blocks delivery events, delaying deliveries. **ED:** ED-M5. | 4 |
| **SR8 - Third-party AI / Cloud provider** (External, non-malicious) | ER6.3 Unavailability of the data warehouse (EA6, D3) | **Objective (SR8-OV11):** Failure or compromise of hosted data services. A breach or failure at the cloud provider makes the data warehouse unavailable and stops analysis and training. **ED:** ED-T1. | 3 |
|  | ER1.2 Unavailability of the forecasting service (EA1, D3) | **Objective (SR8-OV19):** Outage or compromise of hosted AI services. An outage or breach at the cloud provider takes the forecasting service offline. **ED:** ED-T1. | 3 |
|  | ER5.2 Unavailability of the supplier and delivery risk assessment service (EA5, D2) | **Objective (SR8-OV27):** Outage of hosted risk-assessment services. A cloud provider outage makes the supplier and delivery risk assessment service unavailable. **ED:** ED-T1. | 2 |
| **SR9 - State-sponsored** (External, malicious) | ER7.2 Unauthorized extraction or disclosure of proprietary AI models (EA7, C3) | **Objective (SR9-OV12):** Espionage on proprietary AI models. A state-sponsored actor targets the proprietary models for espionage (weak link to Workshop 1). **ED:** ED-IA6. | 3 |
| **SR10 - Adversarial AI attacker** (External, malicious) | ER7.1 Biased or poisoned AI models (EA7, I2) | **Objective (SR10-OV13):** Poison input data to bias the models. An attacker injects malicious data into inputs or training sets so that the models become biased. **ED:** ED-IA1. | 3 |
|  | ER4.3 Evasion or circumvention of anomaly-detection controls (EA4, I2) | **Objective (SR10-OV14):** Craft inputs that evade anomaly detection. An attacker crafts inputs that slip past the anomaly-detection model. **ED:** ED-IA3. | 3 |
|  | ER2.1 Incorrect replenishment recommendations (EA2, I2) | **Objective (SR10-OV15):** Inject malicious instructions to manipulate AI recommendations. An attacker inserts malicious instructions to steer replenishment recommendations. **ED:** ED-IA7. | 3 |
|  | ER1.1 Inaccurate or biased demand forecasts (EA1, I2) | **Objective (SR10-OV17):** Poison input or training data to bias demand forecasts. An attacker poisons input or training data so that demand forecasts become biased. **ED:** ED-IA1. | 3 |
|  | ER7.3 Reconstruction of training data through model inversion (EA7, C3) | **Objective (SR10-OV30):** Reconstruct sensitive training data from model outputs. An attacker queries the model repeatedly to reconstruct sensitive training data. **ED:** ED-IA5. | 3 |
| **SR11 - Hacktivist** (External, malicious) | ER3.2 Unavailability of the sales platform or order API (EA3, D4) | **Objective (SR11-OV16):** Take the sales platform and order API offline (denial of service). Hacktivists flood the sales platform and order API until orders stop. **ED:** ED-M3. | 4 |

---

## 2. Coverage Analysis of Workshop 1 Feared Events

All 31 Feared Events of the consolidated Workshop 1 report were reviewed. Each one received an explicit coverage decision:

- **Covered:** an existing SR/OV pair already addresses the event.
- **New pair:** an additional SR/OV pair was created.
- **Clarified:** the event is related to an existing pair, whose description was clarified.
- **Not represented:** the event has no SR/OV pair, with a documented justification.

| ER | Feared event | Essential asset | Decision | SR/OV pair(s) | Justification |
| :--- | :--- | :--- | :--- | :--- | :--- |
| ER1.1 | Inaccurate or biased demand forecasts | EA1 | New pair | SR10-OV17, SR4-OV18 | - |
| ER1.2 | Unavailability of the forecasting service | EA1 | New pair | SR8-OV19 | - |
| ER1.3 | Disclosure of historical sales and strategic data | EA1 | Covered | SR5-OV8 | - |
| ER1.4 | Inability to identify the model version used to generate a forecast | EA1 | Clarified | SR3-OV6 | A consequence of untracked model changes. The description of SR3-OV6 now states it. |
| ER2.1 | Incorrect replenishment recommendations | EA2 | Covered | SR10-OV15 | - |
| ER2.2 | Circumvention of human validation for high-value orders | EA2 | Covered | SR2-OV4 | - |
| ER2.3 | Unavailability of the inventory optimization service | EA2 | New pair | SR6-OV20 | - |
| ER2.4 | Unauthorized modification of safety-stock requirements or thresholds | EA2 | New pair | SR2-OV21, SR4-OV22 | - |
| ER3.1 | Loss or unavailability of customer-order records | EA3 | New pair | SR6-OV23 | - |
| ER3.2 | Unavailability of the sales platform or order API | EA3 | Covered | SR11-OV16 | - |
| ER3.3 | Unauthorized disclosure of customers' personal data | EA3 | Covered | SR1-OV1 | - |
| ER3.4 | Failure to deliver orders within the expected timeframe | EA3 | New pair | SR7-OV24 | - |
| ER3.5 | Unauthorized modification of customer-order information | EA3 | Covered | SR1-OV2 | - |
| ER4.1 | Failure to identify abnormal or suspicious activity (false negatives) | EA4 | New pair | SR2-OV25 | - |
| ER4.2 | Excessive false-positive alerts | EA4 | New pair | SR4-OV26 | - |
| ER4.3 | Evasion or circumvention of anomaly-detection controls | EA4 | Covered | SR10-OV14 | - |
| ER5.1 | Inaccurate supplier risk assessment | EA5 | Covered | SR7-OV10 | - |
| ER5.2 | Unavailability of the supplier and delivery risk assessment service | EA5 | New pair | SR8-OV27 | - |
| ER5.3 | Disclosure of supplier contracts and commercial conditions | EA5 | New pair | SR5-OV28 | - |
| ER6.1 | Unauthorized or erroneous corruption of business and historical data | EA6 | Covered | SR4-OV7 | - |
| ER6.2 | Unauthorized disclosure of customer or supplier data | EA6 | New pair | SR6-OV29 | - |
| ER6.3 | Unavailability of the data warehouse | EA6 | Covered | SR8-OV11 | - |
| ER6.4 | Irrecoverable loss of historical business data | EA6 | Covered | SR6-OV9 | - |
| ER7.1 | Biased or poisoned AI models | EA7 | Covered | SR3-OV6, SR10-OV13 | - |
| ER7.2 | Unauthorized extraction or disclosure of proprietary AI models | EA7 | Covered | SR3-OV5, SR9-OV12 | - |
| ER7.3 | Reconstruction of training data through model inversion | EA7 | New pair | SR10-OV30 | - |
| ER7.4 | Undetected model drift | EA7 | Not represented | - | No risk source with an objective leads to it: drift is a gradual degradation (ED-IA9), and Workshop 1 marks its CIA class as "To be validated". |
| ER8.1 | Unauthorized modification of decision and activity logs | EA8 | Covered | SR2-OV3 | - |
| ER8.2 | Failure to record user overrides and their reasons | EA8 | New pair | SR4-OV31 | - |
| ER8.3 | Unauthorized access to logs | EA8 | New pair | SR6-OV32 | - |
| ER8.4 | Loss or unavailability of decision and activity logs | EA8 | New pair | SR4-OV33 | - |

**Summary:** Covered: 14. New pair: 15. Clarified: 1. Not represented: 1. Total: 31 Feared Events.

---

## 3. Assumptions and Notes

- Sources SR1 to SR4 are internal; SR5 to SR11 are external.
- Administrators and data scientists are listed as separate internal sources (SR2, SR3) because their access and targets differ: administrators act on systems, accounts and logs; data scientists act on models and training data.
- SR7 groups suppliers and carriers because they act in the same way (manipulated or compromised data feeds).
- SR4 (inattentive employee) and SR8 (third-party provider) act without malicious intent. They are kept as risk sources because their actions or failures can lead to Feared Events.
- SR9 has no direct Dangerous Event in Workshop 1. It can be kept for completeness or dropped in the scoring step if its relevance is low.
- SR11 was added because the Workshop 1 conclusion lists hacktivists as an example risk source.
- The list of 11 risk sources is based on Workshop 1 and is not exhaustive. Further sources can be added if the team validates them.
- ISO/IEC 27090, Chapter 6 attack types covered: data poisoning (ED-IA1, ED-IA2), evasion (ED-IA3), model inversion (ED-IA5), model theft (ED-IA6) and prompt injection (ED-IA7). Membership inference (ED-IA4) and output injection (ED-IA8) can be added if needed.
- Pairs use the Feared Events of the consolidated Workshop 1 report (draft final report), which is the latest version.
- Severity is derived from the class (C, I, D) of the affected Essential Asset, using the scale in section 1.2.
- Some links between a Feared Event and a Dangerous Event are by extension, because the impacted assets listed in Workshop 1 differ: SR1-OV2 (ED-M6 lists BE2, BE4, BE6), SR5-OV8 and SR5-OV28 (ED-M4 lists BE3, BE6). These links should be validated by the team.
- ER3.4 concerns the timeliness of the business delivery service, not an IT outage. SR7-OV24 treats it through falsified or blocked delivery events; its severity (4) follows the D4 class of EA3.
- ER7.4 (undetected model drift) is not used because Workshop 1 marks its CIA class as "To be validated".
