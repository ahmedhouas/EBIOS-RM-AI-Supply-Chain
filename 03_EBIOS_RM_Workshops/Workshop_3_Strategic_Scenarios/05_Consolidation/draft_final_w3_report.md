# Workshop 3 – Strategic Scenarios

# 1. Ecosystem Definition:

The system under study is an AI-enabled Supply Chain Management Information System (AI-SCMIS) consists of an information system consists of:

- Work stations equipped with monitoring and management dashboards of the AI-SCMIS system.
- Local server that runs the local services and the databases and data warehouse.
- Local server that runs the AI layer of the system.
- Local network (Wi-Fi & Ethernet) to connect the different parts of the system.
- IoT devices to control and monitor warehouse and carriers.
- Internet connection to connect the internal system to external information sources.

The main actors of this system are:

- Internal Employees (Administration, Warehouse sevice, Carrier drivers).
- Clients and Partners (External clients, Suppliers).
- Technical Service Providers (Web Hosting service provider, External API providers: Weather, Suppliers, route status - I am not sure of this term -)
- Software Providers (ERP, WMS,…).
- Suppliers of technical equipment.

# 2. Definition of System Stakeholders

| Category | Stakeholder | Interaction with The system |
| --- | --- | --- |
| Internal | Administration | Monitor the system and metrics reporting work status. |
|  | Warehouse service | Manage data related goods, stocks and orders. |
|  | Finance & accountants service | Manage & Monitor financial data inside the system. |
|  | Sales Service | Manage clients & orders related data |
|  | Carrier Drivers | Provide delivery data |
|  | Information system Admin (DSI) | Configure the system and its  equipment and Manage other stake holders roles and access level. |
|  | Technical Service (Engineers) | Design & implement & Develop the AI layer of the system. |
|  | Website management service | Manage the sales website of the company |
| External | Clients | Explores Company website and place orders. |
|  | Suppliers | Provide Information to the system. |
|  | Software providers | Provide Softwares (ERP, WMS, …) |
|  | Hosting service provider | Hosts the company website. |
|  | Other competitor spare parts companies | They may spy, attack, or alter information inside the company system. |
|  | Cleaning service provider | They have physical access to IT infrastructure, they may cause a corruption. |

# 3. Stakeholders Evaluation

The evaluation of stakeholders depends of 2 factors:

1. Exposure: what level of access the stakeholder has to the study object (AI-SCMIS)
2. Cyber Reliability: How much the company can trust the stakeholder, and at what level he is aware of cybersecurity best practices.

The rating scale used: 1-2: Weak / 3-4: Moderate / 5-6: High

| Stakeholder | Exposure | Cyber Reliability | Observation |
| --- | --- | --- | --- |
| Administration | 5 | 5 | The have the have a deep access to company information. |
| Warehouse service | 2 | 1 | The may insert wrong information to the system, or leak warehouse information unintentionally  |
| Finance & accountants service | 3 | 3 | The are exposed to critical information of the company. |
| Sales Service | 4 | 3 | The are a risque of leaking clients or losing them. |
| Carrier Drivers | 2 | 1 | The may falsify delivery information  |
| Information system Admin (DSI) | 6 | 5 | He has the full control over the system. |
| Technical Service (Engineers) | 6 | 5 | Wrong decision or design of this service means a huge effect on the all other services since they manage the base layer of the system. |
| Website management service | 5 | 5 | Wrong configuration can expose sensitive information to public. |
| Clients | 2 | 1 | The have a limited interaction to system. |
| Suppliers | 4 | 1 | Wrong information provided of them, will falsify the decisions of the AI. |
| Software providers | 6 | 5 |  |
| Hosting service provider | 5 | 5 |  |
| Other competitor spare parts companies | 1 | 1 | High source of threat. |
| Cleaning service provider | 3 | 1 | Physical access to hardware. |

---

# 4. Threat Evaluation of Each Actor

The threat level of each stakeholder is calculated from the two factors evaluated in the previous section:

**Threat level = Exposure / Cyber Reliability**

- A ratio of **1** means the access the stakeholder has matches the trust the company can give them.
- A ratio **above 1** means the stakeholder has more access than the company can trust them with.
- The higher the ratio, the higher the threat.

The classification used:

| Threat level (ratio) | Zone | Meaning |
| --- | --- | --- |
| >= 2 | Critical | Exposure is at least double the reliability. The stakeholder is a critical stakeholder (PPC). |
| > 1 and < 2 | Watch | Exposure is higher than reliability. The stakeholder is monitored. |
| <= 1 | Acceptable | Reliability matches or exceeds exposure. |

| Stakeholder | Exposure | Cyber Reliability | Threat level | Zone | Main threat |
| --- | --- | --- | --- | --- | --- |
| Suppliers | 4 | 1 | 4.00 | Critical | Falsified or wrong data (stocks, prices, delays) misleads the AI decisions. A compromised supplier account can be used as an entry point. |
| Cleaning service provider | 3 | 1 | 3.00 | Critical | Physical access to servers, network equipment and workstations: theft, corruption, rogue USB device, accidental unplugging. |
| Warehouse service | 2 | 1 | 2.00 | Critical | Wrong data entry, unintentional leak of warehouse information, misuse of IoT devices. |
| Carrier Drivers | 2 | 1 | 2.00 | Critical | Falsified delivery data, lost or stolen mobile devices and IoT trackers. |
| Clients | 2 | 1 | 2.00 | Critical | Fraudulent orders, account takeover, attacks through the sales website used as an entry point. |
| Sales Service | 4 | 3 | 1.33 | Watch | Leak of client data, loss of clients, phishing. |
| Information system Admin (DSI) | 6 | 5 | 1.20 | Watch | Compromise of a privileged account gives full control of the system. |
| Technical Service (Engineers) | 6 | 5 | 1.20 | Watch | Design errors, tampering with the AI layer, insecure deployment. |
| Software providers | 6 | 5 | 1.20 | Watch | Supply chain attack through malicious updates or vulnerable ERP / WMS components. |
| Administration | 5 | 5 | 1.00 | Acceptable | Targeted phishing of managers, leak of sensitive information. |
| Finance & accountants service | 3 | 3 | 1.00 | Acceptable | Financial fraud, theft of financial data. |
| Website management service | 5 | 5 | 1.00 | Acceptable | Wrong configuration exposing sensitive information to the public. |
| Hosting service provider | 5 | 5 | 1.00 | Acceptable | Provider outage or breach leading to data exposure and website unavailability. |
| Other competitor spare parts companies | 1 | 1 | 1.00 | Special case | Espionage, intrusion, alteration of information. |

**Note on competitors:** competitors are not a normal stakeholder. They have no legitimate access to the system but they have the intention to harm the company, so the ratio does not reflect their threat. They are treated as a **risk source** (a high source of threat, as mentioned in the stakeholders evaluation), not rated by the ratio.

**Note on external API providers:** the external API providers (weather, traffic and road conditions, suppliers) mentioned in the ecosystem definition are not in the stakeholders table. They provide data to the AI layer, so they carry a data integrity risk similar to the suppliers, and should be considered with them.

# 5. PPC - Parties Prenantes Critiques (Critical Stakeholders)

The PPCs are the stakeholders in the **Critical zone** (threat level >= 2).

| PPC | Threat level | Why it is critical | Possible security measures |
| --- | --- | --- | --- |
| Suppliers | 4.00 | They have a significant access to the system (4/6) with a very low cyber reliability (1/6). Wrong or falsified data directly falsifies the decisions of the AI. | Validation and anomaly detection of supplier data, authenticated APIs, security clauses in contracts. |
| Cleaning service provider | 3.00 | They have physical access to the IT infrastructure with no cybersecurity awareness. | Locked server room, supervised or scheduled access, access logs, disabled USB ports. |
| Warehouse service | 2.00 | They manage goods, stocks and orders data without cybersecurity awareness, so errors and leaks are likely. | Awareness training, input controls, least privilege access. |
| Carrier Drivers | 2.00 | They provide delivery data and may falsify it, and they use mobile devices outside the company. | Strong authentication on mobile apps, cross-checking with IoT / GPS data, remote wipe of lost devices. |
| Clients | 2.00 | They use the internet-facing website, which can be used for fraud or as an entry point to the system. | Web application firewall, rate limiting, strong authentication, separation of the website from the internal network. |

**Stakeholders to monitor (not PPC by the ratio):** the **DSI, Technical Service (Engineers) and Software providers** are in the watch zone. Their ratio is low only because they are reliable, but their exposure is the maximum (6/6), so any compromise of them would have a huge impact on the whole system. They should be kept in mind when building the strategic scenarios.

**Competitors** are kept as a **risk source** and not as a PPC.

# 6. Summary

- **5 PPCs:** Suppliers, Cleaning service provider, Warehouse service, Carrier Drivers, Clients.
- **3 stakeholders to monitor for their high impact:** DSI, Technical Service (Engineers), Software providers.
- **1 risk source:** Competitor spare parts companies.

---

# 7. Construction of the Strategic Scenarios

## 7.1 Principle

A strategic scenario describes how a **risk source** reaches its **target objective** (OV) and causes a **feared event** (ER) of Workshop 1, by following a path in the ecosystem defined in section 1. Two kinds of path are used:

| Path type | Definition |
| --- | --- |
| **Direct path** | The risk source reaches the target on its own: it attacks the AI-SCMIS components itself, or it uses the access it already has (insider). No stakeholder is used as a relay. |
| **Indirect path** | The risk source goes through a **stakeholder of the ecosystem** (a PPC or a stakeholder to monitor) that is used as a relay, an entry point or a source of falsified data. |

The stakeholders used as relays come from Part 2: the 5 PPCs (Suppliers, Cleaning service provider, Warehouse service, Carrier Drivers, Clients) and the 3 stakeholders to monitor (DSI, Technical Service, Software providers). The Hosting provider, Sales Service and Administration are also used where the threat table of section 4 gives them a relevant threat.

## 7.2 From couples to scenarios

The 16 retained couples are grouped into **14 strategic scenarios**. The only grouping is the one proposed in Workshop 2 (section 5): the three ransomware couples describe the same attack on different assets, so they are merged into one scenario (SS1). Every other couple is one scenario. The attack families of Workshop 2 are kept.

| Scenario | Family (Workshop 2) | Risk source | Target objective (OV) | Feared event (ER) | Couple(s) | Relevance (W2) |
| --- | --- | --- | --- | --- | --- | --- |
| SS1 | Ransomware | SR6 Organised cyber criminals | OV9, OV20, OV23: encrypt or destroy historical data, replenishment systems and customer-order records | ER6.4, ER2.3, ER3.1 | SR6-OV9, SR6-OV20, SR6-OV23 | 16 |
| SS2 | Data theft | SR6 Organised cyber criminals | OV29: steal customer or supplier data for sale or extortion | ER6.2 | SR6-OV29 | 10.5 |
| SS3 | Data theft | SR1 Malicious employee | OV1: steal or disclose customers' personal data | ER3.3 | SR1-OV1 | 7.5 |
| SS4 | Data theft | SR5 Competitor | OV8: obtain historical sales and strategic data | ER1.3 | SR5-OV8 | 7.5 |
| SS5 | Data theft | SR5 Competitor | OV28: obtain supplier contracts and commercial conditions | ER5.3 | SR5-OV28 | 6 |
| SS6 | Administrator abuse | SR2 Malicious system administrator | OV4: bypass human validation of high-value orders | ER2.2 | SR2-OV4 | 9 |
| SS7 | Administrator abuse | SR2 Malicious system administrator | OV25: disable or weaken anomaly detection to hide fraud | ER4.1 | SR2-OV25 | 9 |
| SS8 | Administrator abuse | SR2 Malicious system administrator | OV3: alter or erase logs to hide malicious activity | ER8.1 | SR2-OV3 | 6 |
| SS9 | Administrator abuse | SR2 Malicious system administrator | OV21: change safety-stock thresholds without authorisation | ER2.4 | SR2-OV21 | 6 |
| SS10 | AI model attacks | SR3 Malicious data scientist / ML engineer | OV5: steal the proprietary AI models | ER7.2 | SR3-OV5 | 9 |
| SS11 | AI model attacks | SR3 Malicious data scientist / ML engineer | OV6: tamper with models or training data | ER7.1 | SR3-OV6 | 6 |
| SS12 | Evasion of detection | SR10 Adversarial AI attacker | OV14: craft inputs that evade anomaly detection | ER4.3 | SR10-OV14 | 7.5 |
| SS13 | Denial of service and delivery disruption | SR11 Hacktivist | OV16: take the sales platform and order API offline | ER3.2 | SR11-OV16 | 5 (exception: severity 4) |
| SS14 | Denial of service and delivery disruption | SR7 Fraudulent / compromised supplier / carrier | OV24: falsify or block delivery events to delay deliveries | ER3.4 | SR7-OV24 | 5 (exception: severity 4) |

# 8. Attack Paths (Direct and Indirect)

Each path is written as: risk source → entry point or relay → supporting asset reached → feared event. The supporting assets are those of the Workshop 1 report (section 3.2) and the components of section 1 of this workshop. Paths are hypotheses built from the case study; the technical detail of each step is the subject of Workshop 4.

## 8.1 Direct and indirect paths per scenario

| Scenario | Direct path | Indirect path(s), with the stakeholder used as relay |
| --- | --- | --- |
| **SS1** Ransomware | SR6 → attack on an exposed service or remote access of the local servers → encryption of the database and data warehouse server, the AI server and the ERP / WMS → ER6.4, ER2.3, ER3.1. | (a) **Software providers**: malicious or vulnerable ERP / WMS update → servers → ER2.3, ER3.1. (b) **Cleaning service provider**: rogue USB device or physical access to the server room → local server → ER6.4. (c) **Clients**: attack through the sales website and order API → internal network → ER3.1. (d) **Suppliers**: compromised supplier account or portal → integration service → databases → ER6.4. (e) **Warehouse service / Sales Service**: phishing → workstation → local network → ER2.3. |
| **SS2** Data theft by criminals | SR6 → intrusion on the operational database and data warehouse → exfiltration of customer and supplier data → extortion or sale → ER6.2. | (a) **Clients**: account takeover on the sales website → customer data → ER6.2. (b) **Sales Service**: phishing of a workstation with access to client data → ER6.2. (c) **Suppliers**: compromised supplier account → supplier data → ER6.2. (d) **Hosting service provider**: breach of the hosted website → exposed data → ER6.2. |
| **SS3** Malicious employee, personal data | SR1 (employee with legitimate access to order and customer data) → copy of customer data (USB, email, export) → disclosure or sale → ER3.3. | None identified. The insider uses the access he already has. |
| **SS4** Competitor, sales and strategic data | SR5 → intrusion on the sales platform or internal network → historical sales data → ER1.3. | (a) **Sales Service**: targeted phishing or approach of an employee → sales data → ER1.3. (b) **Hosting service provider**: breach of the hosting environment → ER1.3. (c) **Cleaning service provider**: physical access to workstations or servers → ER1.3. |
| **SS5** Competitor, supplier contracts | SR5 → intrusion on the ERP / procurement data → supplier contracts and conditions → ER5.3. | (a) **Suppliers**: contract information obtained through a supplier or its account → ER5.3. (b) **Administration**: targeted phishing of a manager who holds contracts → ER5.3. (c) **Software providers**: weakness in the ERP used to store contracts → ER5.3. |
| **SS6** Administrator bypasses validation | SR2 (DSI, full control over roles and access levels) → changes approval rules or role rights → high-value orders pass without human validation → ER2.2. | Variant to assess in Workshop 4: collusion with a **Supplier** contact to place orders that are not checked. |
| **SS7** Administrator weakens detection | SR2 (DSI) → changes the configuration or rules of the anomaly detection service → fraud is no longer flagged → ER4.1. | Through **Technical Service (Engineers)**: the administrator uses their access to the AI layer to disable or weaken the model. |
| **SS8** Administrator alters logs | SR2 (DSI) → privileged access to the logging system → alteration or deletion of decision and activity logs → ER8.1. | None identified. The administrator controls the logs directly. |
| **SS9** Administrator changes thresholds | SR2 (DSI) → ERP / inventory configuration → safety-stock thresholds changed → ER2.4. | None identified. The administrator uses his own access. |
| **SS10** Engineer steals models | SR3 (Technical Service) → access to the model registry and training pipeline → copy of the models outside the company → ER7.2. | None identified. The engineer uses the access he already has. |
| **SS11** Engineer tampers with models | SR3 (Technical Service) → model registry or training pipeline → modified models or poisoned training data → ER7.1. | Through **Suppliers and external API providers**: falsified input data is used as a cover or a vector for the poisoning of training data → ER7.1. |
| **SS12** Evasion of detection | SR10 → crafted but valid-looking orders submitted through the public sales platform and order API → anomaly detection does not flag them → ER4.3. | (a) **Clients**: fraudulent or taken-over client accounts used to submit the crafted orders. (b) **Suppliers / Carrier Drivers**: falsified data entered through their interfaces to hide an abnormal pattern. |
| **SS13** Hacktivist denial of service | SR11 → traffic flood on the sales website and order API → platform unavailable → ER3.2. | **Hosting service provider**: attack on the shared hosting infrastructure of the website → ER3.2. |
| **SS14** Delivery disruption | SR7 (supplier or carrier, through its authorised interface) → falsified or blocked delivery events sent to the system → AI and managers see false delays or no information → ER3.4. | (a) **Carrier Drivers**: lost, stolen or manipulated mobile devices and IoT trackers send false data. (b) **Suppliers and external API providers** (route status): a compromised feed provides false data. |

## 8.2 Map of attack paths through the stakeholders

The map shows the indirect paths of the PPCs and of the stakeholders to monitor. The direct paths (insiders and direct attacks) are in the table above. The labels are the scenario identifiers.

```mermaid
flowchart LR
  subgraph SRC["Risk sources"]
    SR6["SR6 Cyber criminals"]
    SR5["SR5 Competitor"]
    SR7["SR7 Fraudulent supplier / carrier"]
    SR10["SR10 Adversarial AI attacker"]
    SR11["SR11 Hacktivist"]
    SR3["SR3 ML engineer"]
  end
  subgraph PPC["PPC (critical stakeholders)"]
    SUP["Suppliers"]
    CLE["Cleaning service provider"]
    WH["Warehouse service"]
    CAR["Carrier Drivers"]
    CLI["Clients"]
  end
  subgraph MON["Stakeholders to monitor"]
    SOFT["Software providers"]
    TECH["Technical Service"]
  end
  HOST["Hosting service provider"]
  SYS["AI-SCMIS: servers, databases, AI layer, sales platform"]

  SR6 -->|"SS1, SS2"| SUP
  SR6 -->|"SS1"| CLE
  SR6 -->|"SS1"| WH
  SR6 -->|"SS1, SS2"| CLI
  SR6 -->|"SS1"| SOFT
  SR5 -->|"SS5"| SUP
  SR5 -->|"SS4"| CLE
  SR5 -->|"SS4"| HOST
  SR7 -->|"SS14"| CAR
  SR7 -->|"SS14"| SUP
  SR10 -->|"SS12"| CLI
  SR11 -->|"SS13"| HOST
  SR3 -->|"SS11"| SUP
  SR3 -.->|"SS10, SS11 direct"| TECH

  SUP --> SYS
  CLE --> SYS
  WH --> SYS
  CAR --> SYS
  CLI --> SYS
  SOFT --> SYS
  TECH --> SYS
  HOST --> SYS
