# Workshop 2 – Risk Sources and Target Objectives (SR/OV)

**Section 1:** Threat Sources Identification

**Section 2:** Initial SR/OV inventory

**Section 3:** Evaluation Criteria 

**Section 4:** Scoring grid

**Section 5:** Selection of Retained SR/OV Couples

**Section 6:** Map of Risk Sources

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

## 3. Evaluation Criteria

Each SR/OV couple is scored on three criteria, from 1 to 4. The score applies to the couple (the source and this specific objective), not to the source in general.

| Level | Motivation (how much the source wants it) | Resources (what the source can do) | Activity (how often it acts in this area) |
|---|---|---|---|
| 1 | Very low | Very limited, no special skills or access | Rare |
| 2 | Low | Limited, basic tools or access | Occasional |
| 3 | Strong | Significant, skilled or privileged access | Frequent |
| 4 | Very strong | Extensive, expert team or full access | Very frequent |

**Relevance rule (project assumption):**

`Relevance = Motivation × (Resources + Activity) / 2` (range 1 to 16)

A low motivation lowers the result even when the source is strong.

| Relevance | Level |
|---|---|
| 1 to 4 | Low |
| 5 to 8 | Medium |
| 9 to 12 | High |
| 13 to 16 | Very high |

---

## 4. Scoring Grid and Relevance

Severity comes from the inventory (derived from the Workshop 1 class of the affected asset).

| Couple | M | R | A | Relevance | Level | Sev. | Justification |
|---|---|---|---|---|---|---|---|
| SR1-OV1 | 3 | 3 | 2 | 7.5 | Medium | 3 | Personal data has resale value; an employee already has access; insider theft is occasional. |
| SR1-OV2 | 2 | 3 | 2 | 5 | Medium | 3 | Altering orders brings less direct gain and is easy to trace. |
| SR2-OV3 | 2 | 4 | 2 | 6 | Medium | 3 | Erasing logs is a means to hide another action; the admin controls the logs. |
| SR2-OV4 | 3 | 4 | 2 | 9 | High | 3 | Bypassing validation of large orders gives direct financial gain; the admin controls approvals. |
| SR3-OV5 | 3 | 4 | 2 | 9 | High | 3 | Stolen models have commercial value; the ML engineer has direct access to the registry. |
| SR3-OV6 | 2 | 4 | 2 | 6 | Medium | 3 | Sabotaging own employer's model is rarer than theft; same direct access. |
| SR4-OV7 | 1 | 3 | 4 | 3.5 | Low | 3 | No intent (accidental error); mistakes are frequent; normal access to data. |
| SR5-OV8 | 3 | 2 | 3 | 7.5 | Medium | 2 | Clear commercial motive; data must be obtained from outside; commercial espionage is fairly frequent. |
| SR6-OV9 | 4 | 4 | 4 | 16 | Very high | 3 | Financial motive; skilled groups; ransomware against companies is very frequent. |
| SR7-OV10 | 2 | 3 | 2 | 5 | Medium | 2 | Limited gain for the supplier; already feeds data into the system; low impact (class I1). |
| SR8-OV11 | 1 | 3 | 3 | 3 | Low | 3 | Unintentional failure; provider controls the infrastructure; outages and breaches do occur. |
| SR9-OV12 | 1 | 4 | 1 | 2.5 | Low | 3 | Very strong resources, but a regional distributor is not a likely target. |
| SR10-OV13 | 2 | 3 | 2 | 5 | Medium | 3 | Poisoning inputs needs access to sensors or external feeds, which is difficult. |
| SR10-OV14 | 3 | 3 | 2 | 7.5 | Medium | 3 | A fraudster has a strong reason to evade detection. |
| SR10-OV15 | 2 | 3 | 1 | 4 | Low | 3 | The case study describes no chatbot or LLM, so prompt injection is unlikely (assumption). |
| SR11-OV16 | 2 | 2 | 3 | 5 | Medium | 4 | DoS attacks are frequent, but motivation against this company is weak. Severity is critical (D4). |

---

## 5. Selection of Retained SR/OV Couples

**Threshold:** a couple is retained if its relevance is **6 or more**.
**Exception:** a couple below 6 is also retained if its severity is 4 (critical).

### 5.1 Retained couples (9)

| Couple | Relevance | Source | Objective | Feared event | Why retained |
|---|---|---|---|---|---|
| SR6-OV9 | 16 | Organised cybercriminals | Encrypt or destroy historical data for ransom | ER6.4 | Maximum score; ransomware is frequent and the loss is serious. |
| SR2-OV4 | 9 | Malicious system administrator | Bypass human validation of high-value orders | ER2.2 | Direct financial gain; the admin controls approvals. |
| SR3-OV5 | 9 | Malicious data scientist / ML engineer | Steal the proprietary AI models | ER7.2 | Model theft is a top concern (class C3). |
| SR1-OV1 | 7.5 | Malicious employee | Steal or disclose customers' personal data | ER3.3 | Insider has easy access to personal data. |
| SR5-OV8 | 7.5 | Competitor | Obtain historical sales and strategic data | ER1.3 | Clear commercial motive. |
| SR10-OV14 | 7.5 | Adversarial AI attacker | Craft inputs that evade anomaly detection | ER4.3 | Strong reason to evade the detection model. |
| SR2-OV3 | 6 | Malicious system administrator | Alter or erase logs to hide malicious activity | ER8.1 | The admin controls the logs and can hide other attacks. |
| SR3-OV6 | 6 | Malicious data scientist / ML engineer | Tamper with models or training data | ER7.1 | Covers the data and model poisoning risk (ED-IA1, ED-IA2). |
| SR11-OV16 | 5 | Hacktivist | Take the sales platform and order API offline | ER3.2 | Exception: severity 4 (class D4). |

### 5.2 Excluded couples (7)

| Couple | Relevance | Reason for exclusion | Handled in |
|---|---|---|---|
| SR1-OV2 | 5 | Lower motivation; order alteration is easy to trace. | Security baseline (access control, logging) |
| SR7-OV10 | 5 | Low impact (ER5.1, class I1). | Supplier contracts |
| SR10-OV13 | 5 | Needs hard access to inputs; the risk is covered by SR3-OV6. | SR3-OV6 and data-quality controls |
| SR10-OV15 | 4 | No chatbot or LLM in the case study. | Re-assess if an LLM is added |
| SR4-OV7 | 3.5 | Accidental error, no intent. | Security baseline (ED-H1) |
| SR8-OV11 | 3 | Unintentional failure of a provider. | Supplier contracts, business continuity plan |
| SR9-OV12 | 2.5 | A state actor has no interest in a regional distributor. | Not handled; low relevance |

---

## 6. Map of Risk Sources

The map shows the 9 retained couples. The number on each arrow is the relevance score. The ER in brackets is the Workshop 1 feared event.

```mermaid
flowchart LR
  subgraph INT["Internal sources"]
    SR1["SR1 Malicious employee"]
    SR2["SR2 Malicious system administrator"]
    SR3["SR3 Malicious data scientist / ML engineer"]
  end
  subgraph EXT["External sources"]
    SR5["SR5 Competitor"]
    SR6["SR6 Organised cybercriminals"]
    SR10["SR10 Adversarial AI attacker"]
    SR11["SR11 Hacktivist"]
  end

  SR1 -->|"7.5"| OV1["OV1 Steal customers' personal data (ER3.3)"]
  SR2 -->|"6"| OV3["OV3 Alter or erase logs (ER8.1)"]
  SR2 -->|"9"| OV4["OV4 Bypass validation of high-value orders (ER2.2)"]
  SR3 -->|"9"| OV5["OV5 Steal proprietary AI models (ER7.2)"]
  SR3 -->|"6"| OV6["OV6 Tamper with models or training data (ER7.1)"]
  SR5 -->|"7.5"| OV8["OV8 Obtain historical sales and strategic data (ER1.3)"]
  SR6 -->|"16"| OV9["OV9 Encrypt or destroy historical data for ransom (ER6.4)"]
  SR10 -->|"7.5"| OV14["OV14 Evade anomaly detection (ER4.3)"]
  SR11 -->|"5 (exception: severity 4)"| OV16["OV16 Take the sales platform offline (ER3.2)"]
