# TASK T08 – Identification of Feared Events and Dangerous Events

**Framework:** EBIOS Risk Manager (EBIOS-RM) | Workshop 1  
**System:** Artificial Intelligence Supply Chain Management Information System (AI-SCMIS)

## 1. Introduction and Scope

Within the framework of Workshop 1 of the EBIOS Risk Manager (EBIOS-RM) methodology, this document addresses Task T08: the identification of Feared Events and Dangerous Events.

The primary objective of this analysis is to determine what the organization seeks to protect against potential losses (Feared Events) and to identify the underlying causes and threats (Dangerous Events) that could lead to these adverse consequences.

This assessment builds upon the previously established Asset Inventory, which distinguishes between Essential Assets and Supporting Assets, as well as their classification according to the Confidentiality, Integrity, and Availability (CIA) triad.

Given that the Artificial Intelligence Supply Chain Management Information System (AI-SCMIS) relies extensively on artificial intelligence to support supply chain decision-making, conventional cybersecurity threats alone are insufficient to address its entire threat landscape. Consequently, this analysis incorporates AI-specific threats, drawing on the security considerations associated with the ISO/IEC 27090 standard (Cybersecurity – Artificial Intelligence). The resulting assessment provides a structured security baseline for subsequent EBIOS-RM workshops, particularly Workshop 2 (Risk Sources) and Workshop 3 (Strategic Risk Scenarios).

## 2. Methodology and Key Definitions

### 2.1 Feared Event (ER - Événement Redouté)
A Feared Event represents the negative consequence for the organization resulting from the compromise of an Essential Asset. Such consequences may include financial losses, operational disruptions, legal and regulatory sanctions, reputational damage, and loss of competitive advantage. Feared Events are assessed according to their impact on the three fundamental security properties:
* **Confidentiality (C):** Protection against unauthorized disclosure of information.
* **Integrity (I):** Protection against unauthorized modification, corruption, or destruction of information.
* **Availability (A):** Assurance that systems and information remain accessible when required.

### 2.2 Dangerous Event (ED - Événement Dangereux)
A Dangerous Event is an action, incident, technical failure, or environmental phenomenon affecting one or more Supporting Assets and potentially triggering a Feared Event. Examples include ransomware attacks, human errors, cloud infrastructure failures, and attacks targeting artificial intelligence models.

### 2.3 Identification Approach
The analysis follows a structured approach:
1. Identify the Essential Assets of the AI-SCMIS.
2. Determine the Feared Events associated with each Essential Asset.
3. Identify the Dangerous Events capable of triggering these Feared Events.
4. Classify Dangerous Events into five categories: Natural and Environmental Threats; Human Non-Malicious Threats; Human Malicious Threats (Cyberattacks); Technical Threats; and AI-Specific Threats.

---

## 3. Identification of Feared Events (ER) by Essential Asset

### 3.1 Demand Forecasting (BE1)
| ID | Feared Event | Business Impact | Impacted CIA Property |
| --- | --- | --- | --- |
| ER1.1 | Inaccurate or biased demand forecasts | Overstocking, stockouts, financial losses, and inadequate planning. | Integrity (I) |
| ER1.2 | Unavailability of the forecasting service | Overstocking, stockouts, financial losses, and inadequate planning. | Availability (A) |
| ER1.3 | Disclosure of historical sales and strategic data | Loss of competitive advantage. | Confidentiality (C) |
| ER1.4 | Lack of model version traceability | Inability to audit or explain business decisions. | Integrity (I) |

### 3.2 Replenishment and Inventory Management (BE2)
| ID | Feared Event | Business Impact | Impacted CIA Property |
| --- | --- | --- | --- |
| ER2.1 | Incorrect replenishment recommendations | Capital immobilization, excessive inventory, or stockouts. | Integrity (I) |
| ER2.2 | Circumvention of human validation for high-value orders | Unauthorized financial commitments and potential internal fraud. | Integrity (I) |
| ER2.3 | Unavailability of the inventory optimization service | Disruption of purchasing operations and supply chain activities. | Availability (A) |
| ER2.4 | Unauthorized modification of safety stock thresholds | Unexpected stockouts or excessive storage costs. | Integrity (I) |

### 3.3 Order and Delivery Management (BE3)
| ID | Feared Event | Business Impact | Impacted CIA Property |
| --- | --- | --- | --- |
| ER3.1 | Loss or unauthorized modification of customer orders | Undelivered orders, legal disputes, and reputational damage. | Integrity (I), Availability (A) |
| ER3.2 | Unavailability of the sales platform or order API | Interruption of order processing and direct revenue losses. | Availability (A) |
| ER3.3 | Disclosure of customers' personal data | Law No. 18-07 sanctions and loss of customer trust | Confidentiality (C) |
| ER3.4 | Unexpected delivery delays | Customer dissatisfaction and contractual penalties. | Availability (A) |

### 3.4 Anomaly and Fraud Detection (BE4)
| ID | Feared Event | Business Impact | Impacted CIA Property |
| --- | --- | --- | --- |
| ER4.1 | Failure to detect actual fraudulent activities (false negatives) | Financial losses, collusion, and inventory theft. | Integrity (I) |
| ER4.2 | Excessive false-positive alerts | Increased workload and reduced confidence in the AI-based detection system. | Availability (A) |
| ER4.3 | Circumvention of the fraud detection model | Fraudulent activities remain undetected. | Integrity (I) |

### 3.5 Supplier and Delivery Risk Assessment (BE5)
| ID | Feared Event | Business Impact | Impacted CIA Property |
| --- | --- | --- | --- |
| ER5.1 | Inaccurate supplier risk assessment | Unexpected delays and supply chain disruptions. | Integrity (I) |
| ER5.2 | Unavailability of the risk assessment service | Purchasing decisions made without reliable risk information. | Availability (A) |
| ER5.3 | Disclosure of supplier contracts and commercial conditions | Loss of negotiating power and competitive advantage. | Confidentiality (C) |

### 3.6 Business and Historical Data (BE6)
| ID | Feared Event | Business Impact | Impacted CIA Property |
| --- | --- | --- | --- |
| ER6.1 | Corruption or loss of historical data | Unreliable AI models and loss of organizational knowledge. | Integrity (I), Availability (A) |
| ER6.2 | Unauthorized disclosure of customer or supplier data | Legal sanctions and reputational damage. | Confidentiality (C) |
| ER6.3 | Unavailability of the data warehouse | Interruption of analytical activities and AI model training. | Availability (A) |

### 3.7 AI Models and Training Data (BE7)
| ID | Feared Event | Business Impact | Impacted CIA Property |
| --- | --- | --- | --- |
| ER7.1 | Biased or poisoned AI model | Systematically incorrect business decisions. | Integrity (I) |
| ER7.2 | Theft of proprietary AI models | Loss of intellectual property and competitive advantage. | Confidentiality (C) |
| ER7.3 | Reconstruction of training data through model inversion | Disclosure of sensitive or personal information. | Confidentiality (C) |
| ER7.4 | Undetected model drift | Gradual and unnoticed degradation of model performance. | Integrity (I) |

### 3.8 Decision Traceability and Auditability (BE8)
| ID | Feared Event | Business Impact | Impacted CIA Property |
| --- | --- | --- | --- |
| ER8.1 | Loss or unauthorized modification of logs | Inability to audit decisions or provide reliable evidence. | Integrity (I), Availability (A) |
| ER8.2 | Failure to record user overrides | Lack of accountability and difficulty establishing responsibility following an incident. | Integrity (I) |
| ER8.3 | Unauthorized access to logs | Disclosure of sensitive operational information. | Confidentiality (C) |

---

## 4. Identification of Dangerous Events (ED) by Threat Family

### 4.1 Family 1: Natural and Environmental Threats
| ID | Dangerous Event | Targeted Supporting Assets | Impacted Essential Assets |
| --- | --- | --- | --- |
| ED-N1 | Fire or flooding in the data center | Server and cloud infrastructure | BE1 to BE8 |
| ED-N2 | Prolonged power outage | Infrastructure, ERP/WMS | BE2, BE3, BE6 |
| ED-N3 | Widespread network failure affecting the ISP | Network infrastructure | BE1 to BE8 |

### 4.2 Family 2: Human Non-Malicious Threats (Human Errors)
| ID | Dangerous Event | Targeted Supporting Assets | Impacted Essential Assets |
| --- | --- | --- | --- |
| ED-H1 | Data entry error by an operator | ERP/WMS, sales platform | BE2, BE3, BE6 |
| ED-H2 | Incorrect configuration of access permissions or thresholds | Privileged users, AI services | BE2, BE4 |
| ED-H3 | Accidental deletion of data | Operational database, data warehouse | BE6, BE8 |
| ED-H4 | Failure to comply with human validation procedures | Privileged users | BE2, BE8 |
| ED-H5 | Incorrect labeling of training data | Training pipeline, historical data | BE1, BE7 |

### 4.3 Family 3: Human Malicious Threats (Conventional Cyberattacks)
| ID | Dangerous Event | Targeted Supporting Assets | Impacted Essential Assets |
| --- | --- | --- | --- |
| ED-M1 | Ransomware attack targeting ERP/WMS systems | ERP, WMS, operational database | BE2, BE3, BE6 |
| ED-M2 | Phishing attack targeting privileged users | Privileged users, email systems | BE2, BE7, BE8 |
| ED-M3 | Distributed Denial-of-Service (DDoS) attack | Sales platform, order API | BE3 |
| ED-M4 | Unauthorized exfiltration of customer data | Operational database, data warehouse | BE3, BE6 |
| ED-M5 | Supply chain attack through a compromised supplier | Suppliers, carriers, external sources | BE3, BE5 |
| ED-M6 | Malicious insider attack | Privileged users | BE2, BE4, BE6 |
| ED-M7 | Log manipulation to conceal malicious activities | Dashboards, logging system | BE8 |

### 4.4 Family 4: Technical Threats (Failures and Software Defects)
| ID | Dangerous Event | Targeted Supporting Assets | Impacted Essential Assets |
| --- | --- | --- | --- |
| ED-T1 | Cloud service provider outage | Cloud infrastructure | BE1 to BE8 |
| ED-T2 | Database corruption | Operational database, data warehouse | BE6, BE8 |
| ED-T3 | ETL/ELT integration service failure | Integration service | BE1, BE6 |
| ED-T4 | Software defect in an AI service | AI services, model registry | BE1, BE2, BE4 |
| ED-T5 | Synchronization failure between sales and warehouse systems | Integration service, ERP/WMS | BE2, BE3, BE6 |
| ED-T6 | Backup mechanism failure | Infrastructure, database | BE6, BE8 |

### 4.5 Family 5: AI-Specific Threats (ISO/IEC 27090)
| ID | Dangerous Event | Description | Targeted Supporting Assets | Impacted Essential Assets |
| --- | --- | --- | --- | --- |
| ED-IA1 | Data Poisoning | Injection of malicious data into training datasets to bias predictions. | Historical data, training pipeline | BE1, BE2, BE7 |
| ED-IA2 | Direct Model Poisoning | Unauthorized manipulation of an AI model during development or deployment. | Model registry, AI services | BE1, BE2, BE7 |
| ED-IA3 | Evasion Attack | Subtle modification of input data to produce incorrect model outputs. | AI services, input data | BE4, BE5 |
| ED-IA4 | Membership Inference | Determining whether specific information was included in the training dataset. | AI models, training data | BE7 |
| ED-IA5 | Model Inversion | Reconstructing sensitive training information from the outputs of an AI model. | AI models | BE7 |
| ED-IA6 | Model Theft / Exfiltration | Unauthorized extraction or reconstruction of a proprietary AI model. | AI services, model registry | BE7 |
| ED-IA7 | Prompt Injection | Introduction of malicious instructions into prompts to manipulate AI behavior. | User interfaces, AI services | BE1, BE2, BE4 |
| ED-IA8 | Output Injection (XSS) | Generation of malicious scripts through AI-generated outputs. | Dashboards, web interfaces | BE8 |
| ED-IA9 | Undetected Model Drift | Gradual degradation of model performance due to market changes. | Model registry, monitoring tools | BE1, BE4, BE5 |
| ED-IA10 | Training Data Leakage | Unauthorized access to datasets used to train AI models. | Historical data, data warehouse | BE6, BE7 |

---

## 5. Synthesis Matrix and Preliminary Risk Analysis

### 5.1 Cross-Matrix: Essential Assets vs. Dangerous Events
| Essential Asset | Natural Threats | Human Errors | Cyberattacks | Technical Threats | AI-Specific Threats |
| --- | --- | --- | --- | --- | --- |
| BE1 – Demand Forecasting | ED-N1, ED-N3 | ED-H5 | — | ED-T3 | ED-IA1, ED-IA2, ED-IA7, ED-IA9 |
| BE2 – Inventory Management | ED-N1, ED-N2 | ED-H1, ED-H2, ED-H4 | ED-M1, ED-M2, ED-M6 | ED-T4, ED-T5 | ED-IA1, ED-IA2, ED-IA7 |
| BE3 – Order Management | ED-N1, ED-N2, ED-N3 | ED-H1 | ED-M1, ED-M3, ED-M4, ED-M5 | ED-T5 | — |
| BE4 – Anomaly Detection | — | ED-H2 | ED-M6 | ED-T4 | ED-IA3, ED-IA7, ED-IA9 |
| BE5 – Supplier Risk Assessment | — | — | ED-M5 | ED-T4 | ED-IA3, ED-IA9 |
| BE6 – Business and Historical Data | ED-N1, ED-N2 | ED-H3 | ED-M1, ED-M4 | ED-T2 | ED-IA10 |
| BE7 – AI Models and Training Data | ED-N1 | ED-H5 | ED-M2 | ED-T4 | ED-IA1, ED-IA2, ED-IA4, ED-IA5, ED-IA6, ED-IA10 |
| BE8 – Decision Traceability | ED-N1, ED-N3 | ED-H3, ED-H4 | ED-M2, ED-M7 | ED-T2, ED-T6 | ED-IA8 |

### 5.2 Analysis of Major Risks
Based on the identification phase, four Dangerous Events emerge as particularly critical to the security and operational reliability of the AI-SCMIS:
* **Data Poisoning (ED-IA1):** This event directly targets the data that supports the system's intelligence. By introducing corrupted information into historical datasets, an attacker could influence AI predictions and generate systematically inaccurate supply chain forecasts, leading to unexpected stockouts or excessive inventory.
* **Ransomware (ED-M1):** Despite being a conventional threat, it remains highly disruptive. A successful attack against ERP and WMS systems could prevent access to critical operational databases, resulting in the immediate disruption of physical logistics and order processing.
* **Model Theft (ED-IA6):** The unauthorized extraction of proprietary AI models represents a major threat to the organization's intellectual property, undermining its technological investment and competitive position.
* **Undetected Model Drift (ED-IA9):** Unlike conventional cyberattacks, model drift may occur gradually without generating obvious security alerts. If this degradation remains undetected, the organization may continue relying on increasingly inaccurate recommendations, resulting in poor business decisions.

### 5.3 Alignment with ISO/IEC 27090 Mitigation Considerations
| Dangerous Event | Preliminary Mitigation Measures | Relevant Reference |
| --- | --- | --- |
| Data Poisoning (ED-IA1) | Implement strict data integrity controls, data lineage tracking, and validation procedures. | ISO/IEC 27090, Chapter 5 |
| Model Theft (ED-IA6) | Adopt a Zero Trust security architecture, encrypt the model registry, and enforce strict access control. | Security architecture principles |
| Undetected Model Drift (ED-IA9) | Deploy continuous model performance monitoring through MLOps and automated alerts. | ISO/IEC 27090, Chapter 7 |
| Prompt Injection (ED-IA7) | Introduce input validation, filtering mechanisms, and appropriate rate-limiting controls. | AI application security practices |

Although detailed risk treatment will be addressed during Workshop 5, the identification phase already highlights several preliminary security measures.

---

## 6. Conclusion and Handover to Subsequent Workshops

This identification phase has established a structured overview of the cybersecurity threats affecting the AI-SCMIS. By cross-referencing the organization's Essential Assets with a broad range of Dangerous Events, the analysis covers conventional threats (physical incidents, human errors, cyberattacks, and technical failures) as well as emerging threats specifically targeting artificial intelligence systems.

Particular attention has been given to AI-related risks such as Data Poisoning, Model Theft, Prompt Injection, Model Inversion, and Undetected Model Drift, which may directly compromise the reliability and security of AI-driven supply chain operations.

The results of this assessment provide a comprehensive baseline for the subsequent EBIOS-RM workshops:
* **Workshop 2 - Risk Sources:** The team will identify and analyze the entities that could seek to exploit the identified Dangerous Events (e.g., competitors, malicious insiders, hacktivists).
* **Workshop 3 - Strategic Scenarios:** The identified threats and risk sources will be combined to develop realistic attack scenarios illustrating how the organization's mission could be affected.

Ultimately, this work establishes the foundation for a structured risk assessment process, enabling the organization to better understand its exposure, prioritize critical threats, and develop appropriate cybersecurity measures to protect the AI-SCMIS.