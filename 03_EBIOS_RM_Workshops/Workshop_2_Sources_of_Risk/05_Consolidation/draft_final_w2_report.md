# Workshop 2: Risk Sources and Target Objectives (SR/OV)

**Case study:** AI-SCMIS  
**Covers:** Initial SR/OV inventory (risk sources identification, severity scale, SR/OV pairs), evaluation criteria, scoring grid and relevance, selection of retained SR/OV couples, attack families, excluded couples, and map of risk sources

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

## 2. Evaluation Criteria

Each SR/OV couple is scored on three criteria, from 1 to 4. The score applies to the couple (the risk source and this specific objective), not to the source in general.

| Level | Motivation (how much the source wants it) | Resources (what the source can do) | Activity (how often it acts in this area) |
|---|---|---|---|
| 1 | Very low | Very limited, no special skills or access | Rare |
| 2 | Low | Limited, basic tools or access | Occasional |
| 3 | Strong | Significant, skilled or privileged access | Frequent |
| 4 | Very strong | Extensive, expert team or full access | Very frequent |

**Relevance rule (project assumption):**

`Relevance = Motivation × (Resources + Activity) / 2` (range 1 to 16)

A low motivation lowers the result even when the source is strong. Because of the division by 2, relevance can be a decimal (for example 7.5).

| Relevance | Level |
|---|---|
| Up to 4.5 | Low |
| Above 4.5 up to 8.5 | Medium |
| Above 8.5 up to 12.5 | High |
| Above 12.5 | Very high |

**Non-malicious sources (SR4, SR8).** These sources act without intent, so Motivation is set to 1. They therefore score low. Whether they stay in the scoring grid or move entirely to the security baseline is an open point for team validation (see section 4).

---

## 3. Scoring Grid and Relevance

Severity comes from the inventory (derived from the Workshop 1 class of the affected asset).

| Couple | ER | M | R | A | Relevance | Level | Sev. | Justification |
|---|---|---|---|---|---|---|---|---|
| SR1-OV1 | ER3.3 | 3 | 3 | 2 | 7.5 | Medium | 3 | Personal data has resale value; an employee already has access; insider theft is occasional. |
| SR1-OV2 | ER3.5 | 2 | 3 | 2 | 5 | Medium | 3 | Altering orders brings less direct gain and is easy to trace. |
| SR2-OV3 | ER8.1 | 2 | 4 | 2 | 6 | Medium | 3 | Erasing logs is a means to hide another action; the admin controls the logs. |
| SR2-OV4 | ER2.2 | 3 | 4 | 2 | 9 | High | 3 | Bypassing validation of large orders gives direct financial gain; the admin controls approvals. |
| SR2-OV21 | ER2.4 | 2 | 4 | 2 | 6 | Medium | 3 | Less direct gain than bypassing validation; the admin has full access to thresholds. |
| SR2-OV25 | ER4.1 | 3 | 4 | 2 | 9 | High | 3 | Direct motive to hide fraud; the admin controls detection rules. |
| SR3-OV5 | ER7.2 | 3 | 4 | 2 | 9 | High | 3 | Stolen models have commercial value; the ML engineer has direct access to the registry. |
| SR3-OV6 | ER7.1 | 2 | 4 | 2 | 6 | Medium | 3 | Sabotaging the own employer's model is rarer than theft; same direct access. |
| SR4-OV7 | ER6.1 | 1 | 3 | 4 | 3.5 | Low | 3 | No intent (accidental error); mistakes are frequent; normal access to data. |
| SR4-OV18 | ER1.1 | 1 | 3 | 2 | 2.5 | Low | 3 | No intent; mislabelling training data is occasional. |
| SR4-OV22 | ER2.4 | 1 | 3 | 3 | 3 | Low | 3 | No intent; configuration mistakes are fairly frequent. |
| SR4-OV26 | ER4.2 | 1 | 3 | 3 | 3 | Low | 3 | No intent; configuration mistakes are fairly frequent. |
| SR4-OV31 | ER8.2 | 1 | 3 | 3 | 3 | Low | 3 | No intent; validation steps are sometimes skipped under pressure. |
| SR4-OV33 | ER8.4 | 1 | 3 | 2 | 2.5 | Low | 2 | No intent; accidental deletion is occasional. |
| SR5-OV8 | ER1.3 | 3 | 2 | 3 | 7.5 | Medium | 2 | Clear commercial motive; data must be obtained from outside; commercial espionage is fairly frequent. |
| SR5-OV28 | ER5.3 | 3 | 2 | 2 | 6 | Medium | 2 | Real motive, but contracts are harder to reach than sales data (borderline). |
| SR6-OV9 | ER6.4 | 4 | 4 | 4 | 16 | Very high | 3 | Financial motive; skilled groups; ransomware against companies is very frequent. |
| SR6-OV20 | ER2.3 | 4 | 4 | 4 | 16 | Very high | 4 | Same ransomware attack as OV9, on the replenishment systems. |
| SR6-OV23 | ER3.1 | 4 | 4 | 4 | 16 | Very high | 4 | Same ransomware attack as OV9, on the customer-order records (class D4). |
| SR6-OV29 | ER6.2 | 3 | 3 | 4 | 10.5 | High | 3 | Data theft for sale or extortion is very common. |
| SR6-OV32 | ER8.3 | 1 | 3 | 3 | 3 | Low | 2 | Logs have little resale value; they are only a step toward another goal. |
| SR7-OV10 | ER5.1 | 2 | 3 | 2 | 5 | Medium | 2 | Limited gain for the supplier; already feeds data into the system; low impact (class I1). |
| SR7-OV24 | ER3.4 | 2 | 3 | 2 | 5 | Medium | 4 | Same logic as OV10, but the impact is critical (class D4). |
| SR8-OV11 | ER6.3 | 1 | 3 | 3 | 3 | Low | 3 | Unintentional failure; the provider controls the infrastructure; outages and breaches occur. |
| SR8-OV19 | ER1.2 | 1 | 3 | 3 | 3 | Low | 3 | Unintentional; same logic as OV11. |
| SR8-OV27 | ER5.2 | 1 | 3 | 3 | 3 | Low | 2 | Unintentional; same logic as OV11. |
| SR9-OV12 | ER7.2 | 1 | 4 | 1 | 2.5 | Low | 3 | Very strong resources, but a regional distributor is not a likely target. |
| SR10-OV13 | ER7.1 | 2 | 3 | 2 | 5 | Medium | 3 | Poisoning inputs needs access to sensors or external feeds, which is difficult. |
| SR10-OV14 | ER4.3 | 3 | 3 | 2 | 7.5 | Medium | 3 | A fraudster has a strong reason to evade detection. |
| SR10-OV15 | ER2.1 | 2 | 3 | 1 | 4 | Low | 3 | The case study describes no chatbot or LLM, so prompt injection is unlikely (assumption). |
| SR10-OV17 | ER1.1 | 2 | 3 | 2 | 5 | Medium | 3 | Same logic as OV13: hard access to inputs. |
| SR10-OV30 | ER7.3 | 2 | 3 | 1 | 4 | Low | 3 | Needs an exposed, queryable model; the case study does not describe one (assumption). |
| SR11-OV16 | ER3.2 | 2 | 2 | 3 | 5 | Medium | 4 | DoS attacks are frequent, but motivation against this company is weak. Severity is critical (D4). |

---

## 4. Selection of Retained SR/OV Couples

**Threshold:** a couple is retained if its relevance is **6 or more**.  
**Exception:** a couple below 6 is also retained if its severity is 4 (critical).

Result: **16 retained couples** and **17 excluded couples** (total 33).

### 4.1 Retained couples (16)

| Couple | Relevance | Source | Objective | ER | Why retained |
|---|---|---|---|---|---|
| SR6-OV9 | 16 | Organised cyber criminals | Destroy or encrypt historical data for ransom | ER6.4 | Maximum score; ransomware is frequent. |
| SR6-OV20 | 16 | Organised cyber criminals | Encrypt or disable replenishment systems | ER2.3 | Maximum score; critical impact (D4). |
| SR6-OV23 | 16 | Organised cyber criminals | Encrypt or destroy customer-order records | ER3.1 | Maximum score; critical impact (D4). |
| SR6-OV29 | 10.5 | Organised cyber criminals | Steal customer or supplier data for sale or extortion | ER6.2 | Data theft for extortion is very common. |
| SR2-OV4 | 9 | Malicious system administrator | Bypass human validation of high-value orders | ER2.2 | Direct financial gain; the admin controls approvals. |
| SR2-OV25 | 9 | Malicious system administrator | Disable or weaken anomaly detection to hide fraud | ER4.1 | Direct motive to hide fraud. |
| SR3-OV5 | 9 | Malicious data scientist / ML engineer | Steal the proprietary AI models | ER7.2 | Model theft is a top concern (class C3). |
| SR1-OV1 | 7.5 | Malicious employee | Steal or disclose customers' personal data | ER3.3 | Insider has easy access to personal data. |
| SR5-OV8 | 7.5 | Competitor | Obtain historical sales and strategic data | ER1.3 | Clear commercial motive. |
| SR10-OV14 | 7.5 | Adversarial AI attacker | Craft inputs that evade anomaly detection | ER4.3 | Strong reason to evade the detection model. |
| SR2-OV3 | 6 | Malicious system administrator | Alter or erase logs to hide malicious activity | ER8.1 | The admin controls the logs and can hide other attacks. |
| SR2-OV21 | 6 | Malicious system administrator | Change safety-stock thresholds without authorisation | ER2.4 | At the threshold; the admin can cause stockouts or excess stock. |
| SR3-OV6 | 6 | Malicious data scientist / ML engineer | Tamper with models or training data | ER7.1 | Covers the data and model poisoning risk (ED-IA1, ED-IA2). |
| SR5-OV28 | 6 | Competitor | Obtain supplier contracts and commercial conditions | ER5.3 | At the threshold (borderline); to be discussed. |
| SR11-OV16 | 5 | Hacktivist | Take the sales platform and order API offline | ER3.2 | Exception: severity 4 (class D4). |
| SR7-OV24 | 5 | Fraudulent / compromised supplier / carrier | Falsify or block delivery events to delay deliveries | ER3.4 | Exception: severity 4 (class D4). |

### 4.2 Attack families (for Workshop 3)

| Family | Retained couples |
|---|---|
| Ransomware | SR6-OV9, SR6-OV20, SR6-OV23 |
| Data theft | SR1-OV1, SR5-OV8, SR5-OV28, SR6-OV29 |
| Administrator abuse | SR2-OV3, SR2-OV4, SR2-OV21, SR2-OV25 |
| AI model attacks | SR3-OV5, SR3-OV6 |
| Evasion of detection | SR10-OV14 |
| Denial of service and delivery disruption | SR11-OV16, SR7-OV24 |

### 4.3 Excluded couples (17)

| Couple | Relevance | Reason for exclusion | Handled in |
|---|---|---|---|
| SR1-OV2 | 5 | Lower motivation; order alteration is easy to trace. | Security baseline (access control, logging) |
| SR7-OV10 | 5 | Low impact (ER5.1, class I1). | Supplier contracts |
| SR10-OV13 | 5 | Needs hard access to inputs; the risk is covered by SR3-OV6. | SR3-OV6 and data-quality controls |
| SR10-OV17 | 5 | Same reason as SR10-OV13. | SR3-OV6 and data-quality controls |
| SR10-OV15 | 4 | No chatbot or LLM in the case study. | Re-assess if an LLM is added |
| SR10-OV30 | 4 | No exposed, queryable model described. | Re-assess if the model is exposed |
| SR4-OV7 | 3.5 | Accidental error, no intent. | Security baseline (ED-H1) |
| SR4-OV18 | 2.5 | Accidental error, no intent. | Security baseline (ED-H5) |
| SR4-OV22 | 3 | Accidental error, no intent. | Security baseline (ED-H2) |
| SR4-OV26 | 3 | Accidental error, no intent. | Security baseline (ED-H2) |
| SR4-OV31 | 3 | Accidental error, no intent. | Security baseline (ED-H4) |
| SR4-OV33 | 2.5 | Accidental error, no intent. | Security baseline (ED-H3) |
| SR8-OV11 | 3 | Unintentional failure of a provider. | Supplier contracts, business continuity plan |
| SR8-OV19 | 3 | Unintentional failure of a provider. | Supplier contracts, business continuity plan |
| SR8-OV27 | 3 | Unintentional failure of a provider. | Supplier contracts, business continuity plan |
| SR9-OV12 | 2.5 | A state actor has no interest in a regional distributor. | Not handled; low relevance |
| SR6-OV32 | 3 | Logs have little value for criminals; only a step toward another goal. | Access control and phishing awareness |

---

## 5. Map of Risk Sources

The map shows the 16 retained couples. The number on each arrow is the relevance score. The ER in brackets is the Workshop 1 feared event.

```mermaid
flowchart LR
  subgraph INT["Internal sources"]
    SR1["SR1 Malicious employee"]
    SR2["SR2 Malicious system administrator"]
    SR3["SR3 Malicious data scientist / ML engineer"]
  end
  subgraph EXT["External sources"]
    SR5["SR5 Competitor"]
    SR6["SR6 Organised cyber criminals"]
    SR7["SR7 Fraudulent / compromised supplier / carrier"]
    SR10["SR10 Adversarial AI attacker"]
    SR11["SR11 Hacktivist"]
  end

  SR1 -->|"7.5"| OV1["OV1 Steal customers' personal data (ER3.3)"]

  SR2 -->|"6"| OV3["OV3 Alter or erase logs (ER8.1)"]
  SR2 -->|"9"| OV4["OV4 Bypass validation of high-value orders (ER2.2)"]
  SR2 -->|"6"| OV21["OV21 Change safety-stock thresholds (ER2.4)"]
  SR2 -->|"9"| OV25["OV25 Weaken anomaly detection (ER4.1)"]

  SR3 -->|"9"| OV5["OV5 Steal proprietary AI models (ER7.2)"]
  SR3 -->|"6"| OV6["OV6 Tamper with models or training data (ER7.1)"]

  SR5 -->|"7.5"| OV8["OV8 Obtain sales and strategic data (ER1.3)"]
  SR5 -->|"6"| OV28["OV28 Obtain supplier contracts (ER5.3)"]

  SR6 -->|"16"| OV9["OV9 Encrypt or destroy historical data (ER6.4)"]
  SR6 -->|"16"| OV20["OV20 Ransomware on replenishment systems (ER2.3)"]
  SR6 -->|"16"| OV23["OV23 Ransomware on customer-order records (ER3.1)"]
  SR6 -->|"10.5"| OV29["OV29 Steal customer or supplier data (ER6.2)"]

  SR7 -->|"5 (exception: severity 4)"| OV24["OV24 Falsify or block delivery events (ER3.4)"]
  SR10 -->|"7.5"| OV14["OV14 Evade anomaly detection (ER4.3)"]
  SR11 -->|"5 (exception: severity 4)"| OV16["OV16 Take the sales platform offline (ER3.2)"]
