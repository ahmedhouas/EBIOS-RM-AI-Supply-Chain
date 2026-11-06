# Workshop 2 – Preparation Notes

## 1. Objective
Prepare participants for Workshop 2 (Sources of Risk) by reviewing the Workshop 1 results and gathering what is needed to identify sources of risk and their objectives against the AI-SCMIS.

**Terminology.** In these notes, *essential assets* (BE1 to BE8) are the *business values* of the EBIOS RM method. Only the term "essential assets" is used below, as in Workshop 1.

## 2. Documents to review

- [ ] Workshop 1 report: introduction and scope (`introduction.pdf`, `scope.pdf`)
- [ ] AI-SCMIS case study (`02_Preparation/Case_Study`)
- [ ] Essential and supporting assets (`Assets_EBIOS_RM v2.pdf`)
- [ ] Asset owners (`02_Preparation/Stakeholders/Owners_Essential_Assets.pdf`)
- [ ] CIA / DAD classification (`02_Preparation/CIA_DAD_Classification`)
- [ ] Feared events and dangerous events (`Identify feared events.docx`)
- [ ] Security baseline (`Security_baseline_reversed(1).docx`)
- [ ] `Participant_List.md` and `Agenda.md`

## 3. Preparation tasks

### A. Understand the organisation and its assets
- [ ] Review the main business activities (demand forecasting, replenishment, orders and delivery, fraud detection, supplier risk).
- [ ] Identify the most important essential assets (highest classes: replenishment D4, order and delivery D4 and C3, business data C3, AI models C3).
- [ ] Understand the supporting assets and their dependencies.
- [ ] Identify the critical components (AI services, model registry, integration service, data warehouse, cloud infrastructure).
- [ ] Understand the consequences of a disruption of supply chain operations.

Reference: essential assets of Workshop 1

| ID | Essential asset | C | I | D |
|----|-----------------|---|---|---|
| BE1 | Demand forecasting | C2 | I2 | D3 |
| BE2 | Replenishment and inventory management | C2 | I2 | D4 |
| BE3 | Order and delivery management | C3 | I2 | D4 |
| BE4 | Anomaly and fraud detection | C2 | I2 | D3 |
| BE5 | Supplier and delivery risk assessment | C2 | I1 | D2 |
| BE6 | Business and historical data | C3 | I2 | D3 |
| BE7 | AI models and training data | C3 | I2 | D3 |
| BE8 | Decision traceability and auditability | C2 | I2 | D2 |

### B. Identify potential sources of risk (candidates, not confirmed threats)
- [ ] Cybercriminal groups (financially motivated, e.g. ransomware, data theft)
- [ ] Organised groups targeting information systems (targeted, long-term, possibly state-linked)
- [ ] Hacktivists
- [ ] Malicious insiders (privileged users, staff with approval rights)
- [ ] Competitors
- [ ] Suppliers, carriers and external service providers (compromised or malicious)

Note for discussion: accidental human actions are not an intentional source of risk in the usual EBIOS RM approach. They are covered by the human-error dangerous events of Workshop 1 (ED-H1 to ED-H5) and by the security baseline. They are kept in the hypotheses below only to decide how to treat them.

### C. Motivations and capabilities
For each candidate source:
- [ ] Possible motivations
- [ ] Technical capabilities
- [ ] Available resources
- [ ] Access to the information system
- [ ] Relationships with internal or external stakeholders

### D. Potential risk objectives
- [ ] Access supplier or customer information
- [ ] Exfiltrate customer personal data (Law No. 18-07)
- [ ] Steal proprietary AI models, training data or sales data
- [ ] Manipulate inventory records
- [ ] Disrupt demand forecasting
- [ ] Manipulate AI recommendations
- [ ] Evade the fraud detection
- [ ] Conceal actions by altering or deleting logs
- [ ] Extort the organisation (ransomware)
- [ ] Disrupt supply chain operations
- [ ] Compromise the integrity of operational data
- [ ] Disrupt delivery and replenishment

## 4. Initial observations (hypotheses to discuss, drawn from Workshop 1)

| # | Source of risk | Objective | Dangerous event (ED) | Linked feared event (ER) | Essential asset |
|---|----------------|-----------|----------------------|--------------------------|-----------------|
| 1 | Competitor or organised group | Poison training data or the model to distort decisions | ED-IA1, ED-IA2 | ER7.1 Biased or poisoned AI model; ER1.1 Inaccurate demand forecasts | BE7 AI models and training data; BE1 Demand forecasting |
| 2 | Competitor | Steal proprietary models or sales data | ED-IA6, ED-IA10 | ER7.2 Theft of AI models; ER1.3 Disclosure of sales and strategic data | BE7 AI models and training data; BE6 Business and historical data |
| 3 | Malicious insider | Bypass human validation for large orders | ED-M6 | ER2.2 Circumvention of human validation | BE2 Replenishment and inventory management |
| 4 | Cybercriminal group | Disrupt ordering or ERP services and extort the organisation (ransomware) | ED-M1 | ER3.2 Unavailability of sales platform / order API; ER6.3 Unavailability of data warehouse | BE3 Order and delivery management; BE6 Business and historical data |
| 5 | Attacker or malicious insider | Evade fraud detection | ED-IA3, ED-M6 | ER4.3 Circumvention of fraud detection model | BE4 Anomaly and fraud detection |
| 6 | Supplier or external data provider (compromised) | Feed false data to the system | ED-M5 | ER5.1 Inaccurate supplier risk assessment; ER6.1 Corruption of historical data | BE5 Supplier and delivery risk assessment; BE6 Business and historical data |
| 7 | Malicious insider or attacker | Tamper with or delete logs to hide actions | ED-M7 | ER8.1 Loss or modification of logs | BE8 Decision traceability and auditability |
| 8 | Cybercriminal group or organised group | Exfiltrate customer personal data | ED-M4 | ER3.3 Disclosure of customers' personal data; ER6.2 Unauthorized disclosure of customer or supplier data | BE3 Order and delivery management; BE6 Business and historical data |
| 9 | Hacktivist or cybercriminal group | Disrupt the sales platform and order processing (DDoS) | ED-M3 | ER3.2 Unavailability of sales platform / order API | BE3 Order and delivery management |
| 10 | External attacker or malicious user | Manipulate AI recommendations (prompt injection) | ED-IA7 | ER1.1 Inaccurate demand forecasts; ER2.1 Incorrect replenishment recommendations | BE1 Demand forecasting; BE2 Replenishment and inventory management |
| 11 | Accidental error by a privileged user (for discussion, see note in 3.B) | Not an objective: unintentional change of thresholds or data | ED-H2 | ER2.4 Modification of safety stock thresholds | BE2 Replenishment and inventory management |

## 5. Questions to consider
1. Which sources of risk are most relevant to this organisation?
2. What might motivate them?
3. What resources and capabilities might they have?
4. Which essential assets (BE1 to BE8) could they target?
5. What objectives could they pursue against the AI-SCMIS?
6. Which external dependencies (suppliers, carriers, weather and market feeds) increase exposure?
7. How should accidental human actions be treated in the study (see note in 3.B)?

## 6. Missing information to clarify
- The Workshop 1 final report is not yet consolidated (`04_Analysis`, `05_Consolidation`, `06_Final` are empty).
- The degree of automation at the execution stage is not specified in the scope.
- The security baseline is only a list of references; no baseline measures are defined.
- Confirm with the Workshop 1 team that the list of dangerous events (ED) is complete.
- No information yet on past incidents or real threat intelligence for this organisation.

## 7. Workshop information

| Item | Description |
|------|-------------|
| Workshop | Workshop 2 – Sources of Risk |
| Methodology | EBIOS Risk Manager |
| Case study | AI-SCMIS |
| Main output | Identified and characterised sources of risk and their risk objectives |

## 8. Completion

- [ ] Required documents reviewed
- [ ] Preparation tasks completed
- [ ] Initial observations documented (section 4)
- [ ] Questions prepared for discussion

> This is a preparation document. The final sources of risk, their characterisation and objectives are decided during Workshop 2.
