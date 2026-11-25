# Workshop 4 – Operational Scenarios

**EBIOS-RM – AI-Enabled Supply Chain Management Information System (AI-SCMIS)**

## 1. Method

Each strategic scenario of Workshop 3 is broken down into operational scenarios. Every operational scenario has a code **SO[scenario].[number]**, for example **SO1.1** is the first operational scenario of SS1. For each one, the operational scenario table gives the vulnerability that is exploited, its vulnerability score, the attack path in four steps (*Know*, *Enter*, *Find*, *Exploit*), and its likelihood. The 14 strategic scenarios give **28 operational scenarios**.

### 1.1 Hypotheses

- **Network:** The sales website is separated from the internal network. Attacks through the website or its hosting provider reach only the data and services of the website.
- **Gravity:** Taken from Workshop 3 for each strategic scenario (G2 to G4).
- **Impact class:** The impact criterion is *High* when the targeted asset is class C3, I2, D3 or D4 (gravity G3 and G4) and *Medium* when it is class C2, I1 or D2 (gravity G2).
- **Selection rule:** For each strategic scenario, the two paths with the highest likelihood and different entry points are developed (in case of a tie: the direct path, then the most threatening relay of Workshop 3). SS3, SS8, SS9 and SS10 have only a direct path in Workshop 3 (the insider uses his own access), so their two operational scenarios are two different execution channels (local access, then remote or Internet access).
- The attack paths and the weaknesses are hypotheses built from the case study, as stated in Workshop 3. They are not measured facts.

### 1.2 Vulnerability score (out of 10)

The score is the sum of five criteria. The best case for the attacker is **10** and the worst case is **4.5**.

| Criterion | Option | Value | Meaning |
|---|---|---|---|
| Attack vector | Network | 2 | The attack is possible remotely (Internet, supplier portal, email) |
| Attack vector | Local | 0.5 | The attack needs physical access or a local session (USB, workstation, admin console) |
| Attack complexity | Low | 2 | No special condition, easy to repeat |
| Attack complexity | High | 1\* | Needs preparation, a second weakness or the agreement of another person |
| Privileges required | No | 2 | The attacker needs no account on the target |
| Privileges required | Yes | 1 | The attacker needs an account or access rights |
| User interaction | No | 2 | No action from a legitimate user is needed |
| User interaction | Yes | 1\* | A legitimate user must act (open an attachment, install an update) |
| Impact on the targeted criterion | High | 2 | Targeted asset of class C3, I2, D3 or D4 |
| Impact on the targeted criterion | Medium | 1 | Targeted asset of class C2, I1 or D2 |

\* Value not given in the handwritten notes, assumed by symmetry with the other options. To be confirmed by the team.

### 1.3 Likelihood and decision

**Likelihood = Gravity × Vulnerability score.** The result is placed on the scale below, which gives the treatment decision. The maximum is **40** (G4 × 10).

| Likelihood | Decision | Meaning |
|---|---|---|
| 0 to less than 5 | Neglect | The scenario is ignored |
| 5 to less than 15 | Accept | The scenario is accepted and monitored |
| 15 to 25 (included) | Reduce | Security measures are needed to bring the scenario down (Workshop 5) |
| More than 25 | Avoid | The scenario is not tolerable; the cause must be removed or the activity changed |

Check against the handwritten examples: active USB ports on a workstation = 7.5 × 3 = 22.5 (SO3.1, *Reduce*); open Internet access to upload data to the cloud = 9 × 3 = 27 (SO3.2, *Avoid*). The example on log modification was written as 6.5 × 2 = 13 (integrity impact Medium, gravity 2). With the gravity and integrity class of Workshop 3 (SS8: I2, G3), it becomes 7.5 × 3 = 22.5 (SO8.1), the value used here.

## 2. Operational Scenarios

| Code | Strategic scenario | Vulnerability | Score | Attack path | Likelihood (G × score) | Decision |
|---|---|---|---|---|---|---|
| SO1.1 | SS1 – Ransomware (Direct) | Remote-access service of the local servers reachable from the Internet and not fully patched | 9 | **Know:** scan of the company's public addresses. **Enter:** exploit the unpatched service or reuse stolen credentials. **Find:** locate the database and data-warehouse server, the AI server and the ERP/WMS hosts. **Exploit:** delete backups, encrypt the servers, demand a ransom. | 9 × 4 = 36 | Avoid |
| SO1.2 | SS1 – Ransomware (Indirect: Warehouse service, Sales Service) | Staff not trained against phishing; workstations on the same local network as the servers | 9 | **Know:** collect employee names and email addresses. **Enter:** phishing email with a malicious attachment. **Find:** from the workstation, discover the servers on the Wi-Fi/Ethernet network and reuse saved credentials. **Exploit:** encrypt the ERP/WMS data and shared folders. | 9 × 4 = 36 | Avoid |
| SO2.1 | SS2 – Data theft and extortion (Direct) | Database and data-warehouse server reachable through a remote-access service with weak access control | 9 | **Know:** scan of public services. **Enter:** exploit the remote service or use stolen credentials. **Find:** customer and supplier tables in the operational database and the data warehouse. **Exploit:** export the data, then sell it or extort the company. | 9 × 3 = 27 | Avoid |
| SO2.2 | SS2 – Data theft and extortion (Indirect: Clients) | Customer accounts without multi-factor authentication, passwords reused elsewhere | 9 | **Know:** leaked credential lists. **Enter:** credential stuffing on the sales website. **Find:** customer profiles and order history in the accounts. **Exploit:** collect personal data (limited to the website, which is separated from the internal network) and sell it. | 9 × 3 = 27 | Avoid |
| SO3.1 | SS3 – Malicious employee, personal data (Direct, local access) | Workstation with access to customer data and active USB ports, with no control of removable media | 7.5 | **Know:** the employee knows which workstation gives access to customer data. **Enter:** legitimate login. **Find:** customer personal data in the order tools. **Exploit:** copy the data to a USB drive and take it out. | 7.5 × 3 = 22.5 | Reduce |
| SO3.2 | SS3 – Malicious employee, personal data (Direct, Internet access) | Open Internet access from workstations, with no filtering of uploads to external storage | 9 | **Know:** the employee knows the data is reachable. **Enter:** legitimate login. **Find:** export of customer data. **Exploit:** upload the data to a personal cloud space or send it by email. | 9 × 3 = 27 | Avoid |
| SO4.1 | SS4 – Competitor, sales data (Direct) | Sales website and order API return order and sales history without strict access control per account | 8 | **Know:** the competitor identifies the public sales website and the order API. **Enter:** creates a normal client account and calls the API with modified identifiers. **Find:** the endpoints that return the sales history (volumes, prices, customers). **Exploit:** downloads the data (the internal network is not reached, the website being separated). | 8 × 2 = 16 | Reduce |
| SO4.2 | SS4 – Competitor, sales data (Indirect: Sales Service) | Sales staff not trained against targeted phishing; workstations with direct access to the sales history | 8 | **Know:** collect names, roles and email addresses of the sales staff (public sources). **Enter:** targeted phishing email with a malicious attachment or a fake login page. **Find:** from the workstation, the sales history files and the saved data warehouse access. **Exploit:** copy the historical sales and strategic data out of the company. | 8 × 2 = 16 | Reduce |
| SO5.1 | SS5 – Competitor, supplier contracts (Direct) | Remote-access service of the local servers reachable from the Internet and not fully patched | 8 | **Know:** scan of the company's public addresses. **Enter:** exploit the unpatched service or reuse stolen credentials. **Find:** the ERP / procurement database that holds the supplier contracts. **Exploit:** copy the contracts and the commercial conditions. | 8 × 2 = 16 | Reduce |
| SO5.2 | SS5 – Competitor, supplier contracts (Indirect: Administration) | Managers who hold contracts are targeted by phishing, with no strong authentication (no MFA) | 8 | **Know:** identify the managers in charge of supplier contracts (organization chart, professional networks). **Enter:** targeted phishing (fake login page) to steal credentials. **Find:** the contracts in the mailbox, the shared folders or the ERP. **Exploit:** exfiltrate the contracts and the commercial conditions. | 8 × 2 = 16 | Reduce |
| SO6.1 | SS6 – Administrator bypasses order validation (Direct, local access) | Administrator can change approval thresholds and roles without double approval or change history | 7.5 | **Know:** the administrator knows the approval rules. **Enter:** legitimate admin login on the local console. **Find:** approval rules and role rights in the configuration. **Exploit:** remove the validation step or grant approval rights, then place high-value orders unchecked. | 7.5 × 3 = 22.5 | Reduce |
| SO6.2 | SS6 – Administrator bypasses order validation (Indirect variant: collusion with a Supplier contact) | No independent check of orders linked to a supplier contact | 6.5 | **Know:** the administrator and the supplier contact agree on the scheme. **Enter:** admin login. **Find:** orders from that supplier that fall under the approval threshold. **Exploit:** orders are placed and paid without human validation. | 6.5 × 3 = 19.5 | Reduce |
| SO7.1 | SS7 – Administrator weakens anomaly detection (Direct, local access) | Anomaly-detection rules and thresholds editable by the administrator without control or alert | 7.5 | **Know:** the administrator knows the detection rules. **Enter:** legitimate admin login on the local console. **Find:** configuration of the anomaly-detection service. **Exploit:** raise thresholds or disable rules so fraud is no longer flagged. | 7.5 × 3 = 22.5 | Reduce |
| SO7.2 | SS7 – Administrator weakens anomaly detection (Indirect: Technical Service) | Administrator can use engineer accounts to reach the AI layer | 6.5 | **Know:** the administrator identifies who can modify the model. **Enter:** use engineer credentials or access to the AI server. **Find:** the anomaly-detection model and its deployment. **Exploit:** weaken or replace the model. | 6.5 × 3 = 19.5 | Reduce |
| SO8.1 | SS8 – Administrator alters logs (Direct, local access) | Logs stored on the server that the DSI administers, with no write-once storage, no separate copy and no double approval for deletion | 7.5 | **Know:** the administrator knows where the decision and activity logs are stored and how long they are kept. **Enter:** opens a local session on the administration console of the log server with his privileged account. **Find:** the entries that record his malicious actions. **Exploit:** edits or deletes these entries so the activity can no longer be traced. | 7.5 × 3 = 22.5 | Reduce |
| SO8.2 | SS8 – Administrator alters logs (Direct, remote access) | Remote administration of the logging system with a single privileged account and no alert when logs are changed | 9 | **Know:** the administrator knows where the decision and activity logs are stored. **Enter:** opens a remote administration session from outside the premises. **Find:** the entries that record his malicious actions. **Exploit:** edits or deletes these entries without leaving a trace. | 9 × 3 = 27 | Avoid |
| SO9.1 | SS9 – Administrator changes stock thresholds (Direct, local access) | Safety-stock thresholds can be changed in the ERP / inventory configuration without double approval or change history | 7.5 | **Know:** the administrator knows the threshold parameters and how the replenishment AI uses them. **Enter:** opens a local session on the ERP / WMS administration console. **Find:** the thresholds of the targeted products. **Exploit:** lowers or raises the thresholds, causing stockouts or excess stock. | 7.5 × 3 = 22.5 | Reduce |
| SO9.2 | SS9 – Administrator changes stock thresholds (Direct, remote access) | ERP / WMS configuration reachable remotely with the same privileged account, with no approval from a second manager | 9 | **Know:** the administrator knows the threshold parameters and how the replenishment AI uses them. **Enter:** connects remotely to the ERP / WMS configuration interface. **Find:** the thresholds of the targeted products. **Exploit:** changes the thresholds without authorization, causing stockouts or excess stock. | 9 × 3 = 27 | Avoid |
| SO10.1 | SS10 – Engineer steals AI models (Direct, local access) | Active USB ports on the engineers' workstations and the training server, with no control of removable media | 7.5 | **Know:** the engineer knows where the model registry and the training pipeline are. **Enter:** logs in to the model registry with his own account. **Find:** the proprietary models (weights, code, parameters). **Exploit:** copies them to a removable disk and takes them out of the company. | 7.5 × 3 = 22.5 | Reduce |
| SO10.2 | SS10 – Engineer steals AI models (Direct, Internet access) | Open Internet access from the workstations and the AI server, with no filtering of uploads to external storage | 9 | **Know:** the engineer knows where the model registry and the training pipeline are. **Enter:** logs in to the model registry with his own account. **Find:** the proprietary models (weights, code, parameters). **Exploit:** uploads them to a personal cloud storage through the open Internet access. | 9 × 3 = 27 | Avoid |
| SO11.1 | SS11 – Engineer tampers with models / training data (Direct) | Model registry and training pipeline with no version control, no integrity check and no review of changes; engineers have write access | 9 | **Know:** the engineer knows the training pipeline and the datasets used. **Enter:** logs in to the model registry or the pipeline with his own account. **Find:** the model version or the dataset that drives the targeted decisions. **Exploit:** modifies the model or inserts poisoned data so that the recommendations are distorted. | 9 × 3 = 27 | Avoid |
| SO11.2 | SS11 – Engineer tampers with models / training data (Indirect: Suppliers, external API providers) | Supplier and external API data (stocks, prices, delays, route status) enter the training data without validation or anomaly detection | 8 | **Know:** the engineer identifies the supplier and API feeds used for training. **Enter:** uses or injects falsified data through an authorized supplier or API access, as cover. **Find:** the training set built from these feeds. **Exploit:** the poisoned data is learned by the model and the action looks like an external data error. | 8 × 3 = 24 | Reduce |
| SO12.1 | SS12 – Evasion of anomaly detection (Direct) | Public order API accepts well-formed orders; detection thresholds can be guessed by probing | 8 | **Know:** probe the platform with test orders to learn what is flagged. **Enter:** submit orders through the public order API. **Find:** an order pattern that stays under the detection thresholds. **Exploit:** place harmful orders that are not flagged. | 8 × 3 = 24 | Reduce |
| SO12.2 | SS12 – Evasion of anomaly detection (Indirect: Clients) | Fraudulent or taken-over client accounts | 9 | **Know:** obtain stolen client accounts. **Enter:** log in to the sales website. **Find:** the profile of normal orders for that account. **Exploit:** submit crafted orders through the account. | 9 × 3 = 27 | Avoid |
| SO13.1 | SS13 – Denial of service on the sales platform (Direct) | Sales website and order API without rate limiting or denial-of-service protection | 10 | **Know:** identify the public website and the order API. **Enter:** send a flood of requests from many sources. **Find:** the endpoint that saturates first. **Exploit:** the sales platform and order API become unavailable (the internal network is not reached, the website being separated). | 10 × 4 = 40 | Avoid |
| SO13.2 | SS13 – Denial of service on the sales platform (Indirect: Hosting service provider) | Website runs on shared hosting infrastructure | 9 | **Know:** identify the hosting provider. **Enter:** attack the shared infrastructure. **Find:** the website's resources on it. **Exploit:** the website goes down together with the infrastructure. | 9 × 4 = 36 | Avoid |
| SO14.1 | SS14 – Falsified or blocked delivery events (Direct) | Delivery events from suppliers and carriers accepted without strong authentication or cross-check | 9 | **Know:** identify the interface used to send delivery events. **Enter:** use an authorised supplier or carrier access. **Find:** the delivery events used by the AI and the managers. **Exploit:** send false or blocking events so that false delays appear or information is missing. | 9 × 4 = 36 | Avoid |
| SO14.2 | SS14 – Falsified or blocked delivery events (Indirect: Suppliers, external API providers) | External route-status feed trusted by the system without checks | 9 | **Know:** identify the route-status feed. **Enter:** compromise the provider or the feed. **Find:** the feed that goes to the AI layer. **Exploit:** false route data causes wrong delay predictions. | 9 × 4 = 36 | Avoid |

## 3. Score Breakdown

| Code | Attack vector | Attack complexity | Privileges required | User interaction | Impact | Score |
|---|---|---|---|---|---|---|
| SO1.1 | Network (2) | High (1) | No (2) | No (2) | High (2) | 9 |
| SO1.2 | Network (2) | Low (2) | No (2) | Yes (1) | High (2) | 9 |
| SO2.1 | Network (2) | High (1) | No (2) | No (2) | High (2) | 9 |
| SO2.2 | Network (2) | High (1) | No (2) | No (2) | High (2) | 9 |
| SO3.1 | Local (0.5) | Low (2) | Yes (1) | No (2) | High (2) | 7.5 |
| SO3.2 | Network (2) | Low (2) | Yes (1) | No (2) | High (2) | 9 |
| SO4.1 | Network (2) | Low (2) | Yes (1) | No (2) | Medium (1) | 8 |
| SO4.2 | Network (2) | Low (2) | No (2) | Yes (1) | Medium (1) | 8 |
| SO5.1 | Network (2) | High (1) | No (2) | No (2) | Medium (1) | 8 |
| SO5.2 | Network (2) | Low (2) | No (2) | Yes (1) | Medium (1) | 8 |
| SO6.1 | Local (0.5) | Low (2) | Yes (1) | No (2) | High (2) | 7.5 |
| SO6.2 | Local (0.5) | High (1) | Yes (1) | No (2) | High (2) | 6.5 |
| SO7.1 | Local (0.5) | Low (2) | Yes (1) | No (2) | High (2) | 7.5 |
| SO7.2 | Local (0.5) | High (1) | Yes (1) | No (2) | High (2) | 6.5 |
| SO8.1 | Local (0.5) | Low (2) | Yes (1) | No (2) | High (2) | 7.5 |
| SO8.2 | Network (2) | Low (2) | Yes (1) | No (2) | High (2) | 9 |
| SO9.1 | Local (0.5) | Low (2) | Yes (1) | No (2) | High (2) | 7.5 |
| SO9.2 | Network (2) | Low (2) | Yes (1) | No (2) | High (2) | 9 |
| SO10.1 | Local (0.5) | Low (2) | Yes (1) | No (2) | High (2) | 7.5 |
| SO10.2 | Network (2) | Low (2) | Yes (1) | No (2) | High (2) | 9 |
| SO11.1 | Network (2) | Low (2) | Yes (1) | No (2) | High (2) | 9 |
| SO11.2 | Network (2) | High (1) | Yes (1) | No (2) | High (2) | 8 |
| SO12.1 | Network (2) | High (1) | Yes (1) | No (2) | High (2) | 8 |
| SO12.2 | Network (2) | High (1) | No (2) | No (2) | High (2) | 9 |
| SO13.1 | Network (2) | Low (2) | No (2) | No (2) | High (2) | 10 |
| SO13.2 | Network (2) | High (1) | No (2) | No (2) | High (2) | 9 |
| SO14.1 | Network (2) | Low (2) | Yes (1) | No (2) | High (2) | 9 |
| SO14.2 | Network (2) | High (1) | No (2) | No (2) | High (2) | 9 |

## 4. Summary by Strategic Scenario

| Rank | Strategic scenario | Gravity | Paths | Highest likelihood | Decision |
|---|---|---|---|---|---|
| 1 | SS13 – Denial of service on the sales platform | G4 | 2 | 40 (SO13.1) | Avoid |
| 2 | SS1 – Ransomware | G4 | 2 | 36 (SO1.1, SO1.2) | Avoid |
| 3 | SS14 – Falsified or blocked delivery events | G4 | 2 | 36 (SO14.1, SO14.2) | Avoid |
| 4 | SS2 – Data theft and extortion | G3 | 2 | 27 (SO2.1, SO2.2) | Avoid |
| 5 | SS10 – Engineer steals AI models | G3 | 2 | 27 (SO10.2) | Avoid |
| 6 | SS3 – Malicious employee, personal data | G3 | 2 | 27 (SO3.2) | Avoid |
| 7 | SS12 – Evasion of anomaly detection | G3 | 2 | 27 (SO12.2) | Avoid |
| 8 | SS8 – Administrator alters logs | G3 | 2 | 27 (SO8.2) | Avoid |
| 9 | SS9 – Administrator changes stock thresholds | G3 | 2 | 27 (SO9.2) | Avoid |
| 10 | SS11 – Engineer tampers with models / training data | G3 | 2 | 27 (SO11.1) | Avoid |
| 11 | SS6 – Administrator bypasses order validation | G3 | 2 | 22.5 (SO6.1) | Reduce |
| 12 | SS7 – Administrator weakens anomaly detection | G3 | 2 | 22.5 (SO7.1) | Reduce |
| 13 | SS4 – Competitor, sales data | G2 | 2 | 16 (SO4.1, SO4.2) | Reduce |
| 14 | SS5 – Competitor, supplier contracts | G2 | 2 | 16 (SO5.1, SO5.2) | Reduce |

**Result:** 28 operational scenarios in total. Avoid: 14. Reduce: 14. Accept: 0. Neglect: 0. The ranking follows the highest likelihood; scenarios with the same value follow the order of Workshop 3 (gravity, then relevance of Workshop 2). The scenarios to reduce or avoid are the input of Workshop 5 (risk treatment).

## 5. Interpretation and Conclusion

The 14 strategic scenarios give 28 operational scenarios: 14 to avoid, 14 to reduce, none to accept or neglect. Of the 14 strategic scenarios, 10 have at least one operational scenario to avoid (SS13, SS1, SS14, SS2, SS10, SS3, SS12, SS8, SS9, SS11) and 4 are to reduce (SS6, SS7, SS4, SS5).

### 5.1 Risks to avoid (likelihood above 25)

The three strategic scenarios of gravity G4 (SS13 denial of service, SS1 ransomware, SS14 falsified delivery events) reach 36 to 40, because the gravity multiplies the score. Seven scenarios of gravity G3 reach 27 through their remote or Internet channel: data theft by criminals through the website and exposed services (SS2), upload of customer data or models to the cloud (SS3, SS10), remote administration of logs and ERP thresholds (SS8, SS9), modification of the training pipeline (SS11) and evasion through client accounts (SS12). For SS3, SS8, SS9 and SS10, the local channel stays at 22.5 (*Reduce*) while the remote or Internet channel reaches 27 (*Avoid*): the attack vector alone decides the class.

### 5.2 Risks to reduce (15 to 25)

Administrator scenarios SS6 and SS7 reach 22.5 through the local console and 19.5 through collusion or an engineer account. SS4 and SS5 (competitor, gravity G2) reach 16, close to the lower limit of the class, because the impact criterion is *Medium*. These scenarios still need security measures, but with less urgency than the first group.

### 5.3 Directions for Workshop 5

- **Priority:** SS13, SS1 and SS14, then the seven scenarios at 27.
- **Administrator privileges (SS6 to SS9):** separation of duties, double approval, change history, write-once logs with a separate copy, alert on log or threshold changes, no remote administration with a single account.
- **Data leaving the company (SS3, SS10):** control of removable media and filtering of uploads to external storage.
- **Training pipeline (SS11):** version control, integrity checks, review of changes, validation and anomaly detection of supplier and external API data.
- **Inputs and public services (SS2, SS12, SS13):** multi-factor authentication of customer accounts, rate limiting, protection against denial of service, input validation and monitoring of model behaviour.
- **Ransomware and delivery data (SS1, SS14):** patching of exposed services, phishing awareness, backups, strong authentication and cross-checking of supplier, carrier and external feed data.

These are directions, not decisions: the measures are chosen and their residual risk is reassessed in Workshop 5.
