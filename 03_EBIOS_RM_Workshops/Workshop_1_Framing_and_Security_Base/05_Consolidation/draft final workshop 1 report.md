# EBIOS Risk Manager – Workshop 1 Report
## AI-Enabled Supply Chain Management Information System (AI-SCMIS)
 
**Workshop:** 1 – Framing and Security Baseline  
**Report status:** Draft for team review  
**Reference case study:** *AI-Enabled Supply Chain Management Information System – System Description, Architecture, and Multi-Stage AI Workflow*
 
---
 
## 1. Define the Study Scope
 
### 1.1 Strategic Scope
 
The system under study is an AI-enabled Supply Chain Management Information System (AI-SCMIS). Its principal mission is to support supply-chain management through machine-learning models that complement and improve manual or static estimation methods.
 
The system's business value comes from using internal and external data to produce traceable, data-supported recommendations for human managers. The study retains the enterprise-wide scope defined in the project scope document.
 
The essential business objectives are:
 
1. Predict product demand and seasonal variations.
2. Recommend replenishment quantities and the timing of replenishment orders.
3. Identify abnormal orders and supplier risks.
4. Anticipate delivery delays and support alternative logistical plans.
5. Provide human managers with traceable, data-supported decisions.
### 1.2 Operational Scope
 
The study covers the operating workflow and supporting lifecycle through which data is transformed into supply-chain recommendations and actions. The scope document identifies seven stages:
 
1. **Data collection:** Collection of information from internal enterprise systems, supplier portals, and external sources such as market and weather information, as described in the scope document.
2. **Data processing:** Cleaning, standardization, validation, and integration of collected data.
3. **AI model training:** Training machine-learning models to identify patterns used for forecasting, anomaly detection, and other supply-chain functions.
4. **Inference and prediction:** Applying trained models to new operational data to generate forecasts, alerts, and risk estimates.
5. **Decision-making:** Presenting results to human users for review and decision.
6. **Execution:** Carrying out approved decisions, such as placing purchase orders or organizing delivery routes.
7. **Continuous improvement:** Monitoring outcomes and using validated results to support model review and retraining.
The workflow is iterative: operational outcomes can feed back into monitoring and model improvement. The case study describes human review and authorization for consequential actions. The exact degree of automation at every execution point is not specified and is not assumed in this report.
 
---
 
## 2. Define CIA Classes
 
### 2.1 Security Objectives
 
The project uses the CIA triad to describe the security properties that must be protected.
 
| Property | Definition | AI-SCMIS examples |
|---|---|---|
| **Confidentiality (C)** | Information is available only to authorized persons, entities, and processes. | Customer personal data; supplier contracts and commercial conditions. |
| **Integrity (I)** | Information and systems remain accurate, complete, and unaltered except through authorized actions. | Stock records, forecasts, model files, and recommendation data. |
| **Availability (A)** | Information and services are accessible and usable when required by authorized users. | Order processing, ERP/WMS functions, and analytical services. |
 
### 2.2 DAD – Types of Security Compromise
 
The project also uses DAD to describe the forms of compromise associated with loss of CIA properties.
 
| CIA property affected | DAD term | Meaning | AI-SCMIS example |
|---|---|---|---|
| Confidentiality | Disclosure | Information is revealed to an unauthorized party. | Disclosure of customer or supplier information. |
| Integrity | Alteration | Information is changed without authorization or through error. | Alteration of training data leading to inaccurate forecasts. |
| Availability | Destruction / Denial | Information or a service is erased, lost, or made inaccessible. | Ransomware making operational systems inaccessible. |
 
### 2.3 Project Classification Scale
 
The project defines the following security classes. A higher number represents a stronger protection requirement.
 
**Confidentiality**
 
| Class | Level | Meaning |
|---|---|---|
| C1 | Public | Disclosure causes no harm. |
| C2 | Secret | Information is reserved for authorized organizational personnel; disclosure could harm the organization. |
| C3 | Confidential | Highest project-defined confidentiality level; disclosure could cause serious harm. |
 
**Integrity**
 
| Class | Level | Meaning |
|---|---|---|
| I1 | Normal | Errors or alterations have limited consequences and can be corrected. |
| I2 | Intact | Information must remain exact and complete; alteration must be prevented or detected. |
 
**Availability**
 
| Project class | Level | Meaning |
|---|---|---|
| D1 | Normal | Long interruptions are acceptable. |
| D2 | Moderate | Interruptions are tolerated for a limited time. |
| D3 | High | Interruptions are tolerated only for a short time. |
| D4 | Critical | The service should be available almost continuously; interruption has a major impact. |
 
The class definitions above reproduce the project's classification scale. The class assigned to each Essential Asset is given in section 3.1.
 
---
 
## 3. Define the Business and Technical Perimeter
 
### 3.1 Essential Assets
 
Essential assets are the processes and information whose loss or compromise would seriously harm the organization.
 
C: C1 Public, C2 Secret, C3 Confidential. I: I1 Normal, I2 Intact. D: D1 Normal, D2 Moderate, D3 High, D4 Critical.
 
| Ref. | Essential asset | Type | Description | Owner | C | I | D |
|---|---|---|---|---|---|---|---|
| EA1 | Demand forecasting | Process | Machine learning models estimate future demand for each product and warehouse over a planning horizon, using historical sales, seasonality, promotions, lead times and calendar effects. It replaces manual, static estimation and drives all downstream replenishment decisions. | Planning manager | C2 | I2 | D3 |
| EA2 | Replenishment and inventory management | Process | Calculates what quantity to order and when, by combining the demand forecast with current stock, goods already on order, supplier lead times, safety stock, storage capacity and budget constraints. Large or exceptional orders require human approval. | Procurement manager | C2 | I2 | D4 |
| EA3 | Order and delivery management | Process | Covers the full path from the reception of a customer order to warehouse picking, dispatch and delivery through contracted carriers, including shipment tracking and notifications to customers and service centres. | Logistics manager | C3 | I2 | D4 |
| EA4 | 	Anomaly Detection and Fraud Indicators | Process | 	Identifies unusual patterns such as abnormal order quantities, unexpected stock reductions, repeated order changes, or duplicate invoices. An alert is an indicator for investigation, not proof of fraud; authorized staff verify it. | Control manager | C2 | I2 | D3 |
| EA5 | Supplier and delivery risk assessment | Process | Estimates the probability of supplier delay or late delivery from historical lead times, shipment events and supplier performance, and proposes alternatives such as contacting the supplier, reserving alternative stock or comparing approved carriers. | Purchasing manager | C2 | I1 | D2 |
| EA6 | Business and historical data | Information | Orders, point-of-sale history, product catalogues, stock levels, warehouse receipts, purchase orders, supplier lead times, carrier tracking events and approved external indicators (weather, holidays). Includes the limited personal data needed for fulfilment and customer service. | Data owners | C3 | I2 | D3 |
| EA7 | AI models and training data | Information | The trained models (forecasting, optimization, anomaly detection, supplier risk), their versions, evaluation results and approval status, and the datasets used to train them. They are the intellectual property of the organization and the basis of every AI recommendation. | Data / AI manager | C3 | I2 | D3 |
| EA8 | Decision traceability and auditability | Information | Logs of user activity, recommendation details, the model version and input data behind each recommendation, approvals, overrides with their reasons and the resulting actions, so that every decision can be traced and audited. | CISO / governance | C2 | I2 | D2 |
 
### 3.2 Supporting Assets
 
Supporting assets are the elements on which the essential assets rely: they are what attacks target.
 
| Supporting asset | Description | Supports |
|---|---|---|
| ERP, WMS, TMS and inventory system | Core business applications: the ERP for planning, procurement and finance; the WMS for warehouse operations such as put-away and picking; the TMS for routing and carrier management; and the inventory system for on-hand, in-transit and inbound stock. | EA1, EA2, EA3, EA6 |
| Sales platform and order API | The platform through which customer orders are received and the API that transmits them to the operational systems. It is the main entry point of customer data. | EA3, EA4, EA6 |
| Integration service (ETL/ELT, APIs) | Receives and validates records, checks required fields, standardizes units and dates, matches product and supplier identifiers, and flags duplicates, missing values and implausible quantities before the data is used by the models. | EA1, EA2, EA4, EA5, EA6, EA7 |
| Operational database and data warehouse (data lake) | The operational database holds current orders and stock. The historical data store retains approved records for analytics and model training, with data lineage so that model inputs can be traced to their source. | EA1, EA2, EA4, EA5, EA6, EA7, EA8 |
| AI services | Separate services for demand forecasting, inventory recommendations, anomaly detection, supplier risk estimation and delivery-time prediction, running in the live environment on new data. | EA1, EA2, EA4, EA5 |
| Model registry and training pipeline | Records model versions, evaluation results, owners, approval status and deployment dates. Supports controlled training, validation, monitoring for drift, retraining and rollback to a validated version. | EA1, EA2, EA4, EA5, EA7 |
| Dashboards and logging system | Role-specific dashboards (warehouse, procurement, logistics, management) that present recommendations and alerts, and the logs that record user activity, approvals and overrides. | EA2, EA3, EA4, EA5, EA8 |
| IoT sensors, barcode scanners, warehouse terminals | Devices on shipping containers and in warehouses (sensors, RFID, GPS, barcode scanners) that report stock movements, locations and delivery events in real time. | EA2, EA3, EA4, EA5, EA6 |
| Server, cloud and network infrastructure | Servers, cloud hosting, storage and network links that run all applications, databases and models, and connect the organization to its partners. | EA1 to EA8 (all) |
| Privileged users | Administrators, data scientists, data owners and procurement staff with extended access rights to data, models and approval functions. | EA2, EA6, EA7, EA8 |
| Suppliers, carriers and external sources | Supplier portals and the tracking systems of contracted carriers, plus external feeds such as market trends, weather and public holidays that provide inputs to the system. | EA1, EA3, EA5, EA6 |
 
---
 
## 4. Identify Feared Events
 
A Feared Event is a negative consequence for the organization resulting from compromise of an Essential Asset. The events below are associated with the CIA property affected.
 
### 4.1 EA1 – Demand Forecasting
 
| ID | Feared Event | Business impact | CIA |
|---|---|---|---|
| ER1.1 | Inaccurate or biased demand forecasts | Overstocking, stockouts, financial losses, and inadequate planning. | I |
| ER1.2 | Unavailability of the forecasting service | Disruption of forecasting activities and reduced ability to plan replenishment. | A |
| ER1.3 | Disclosure of historical sales and strategic data | Loss of competitive advantage. | C |
| ER1.4 | Inability to identify the model version used to generate a forecast | Inability to reproduce, review, or explain a specific forecast and related decisions. | I |
 
ER1.4 is limited to forecasting-model version traceability. General decision and activity traceability is addressed under EA8.
 
### 4.2 EA2 – Replenishment and Inventory Management
 
| ID | Feared Event | Business impact | CIA |
|---|---|---|---|
| ER2.1 | Incorrect replenishment recommendations | Capital immobilization, excessive inventory, or stockouts. | I |
| ER2.2 | Circumvention of human validation for high-value orders | Unauthorized financial commitments and potential internal misuse. | I |
| ER2.3 | Unavailability of the inventory optimization service | Disruption of purchasing operations and supply-chain activities. | A |
| ER2.4 | Unauthorized modification of safety-stock requirements or thresholds | Unexpected stockouts or excessive storage costs. | I |
 
The case study includes safety-stock requirements in replenishment calculations. The detailed threshold-management process is not specified.
 
### 4.3 EA3 – Order and Delivery Management
 
| ID | Feared Event | Business impact | CIA |
|---|---|---|---|
| ER3.1 | Loss or unavailability of customer-order records | Orders may not be processed or fulfilled, causing potential revenue loss, disputes, and reputational damage. | A |
| ER3.2 | Unavailability of the sales platform or order API | Interruption of order processing and potential revenue losses. | A |
| ER3.3 | Unauthorized disclosure of customers' personal data | Loss of customer trust and potential legal or regulatory consequences, subject to applicable legal assessment. | C |
| ER3.4 | Failure to deliver orders within the expected timeframe | Customer dissatisfaction, contractual consequences, and disruption of the delivery service. | A |
| ER3.5 | Unauthorized modification of customer-order information | Incorrect order fulfilment, disputes, financial loss, and reputational damage. | I |
 
ER3.4 concerns the timeliness of the business delivery service and does not automatically indicate an IT system outage.
 
### 4.4 EA4 – Anomaly and Fraud Detection
 
| ID | Feared Event | Business impact | CIA |
|---|---|---|---|
| ER4.1 | Failure to identify abnormal or suspicious activity (false negatives) | Suspicious activity may remain undetected and uninvestigated, potentially resulting in financial or inventory losses. | I |
| ER4.2 | Excessive false-positive alerts | Alert fatigue, increased investigation workload, delayed review of relevant alerts, and reduced confidence in detection results. | I |
| ER4.3 | Evasion or circumvention of anomaly-detection controls | Relevant abnormal patterns may not be flagged, allowing potentially harmful activity to remain undetected. | I |
 
Anomaly alerts are signals for investigation and are not proof that fraud has occurred.
 
### 4.5 EA5 – Supplier and Delivery Risk Assessment
 
| ID | Feared Event | Business impact | CIA |
|---|---|---|---|
| ER5.1 | Inaccurate supplier risk assessment | Unexpected delays and supply-chain disruptions. | I |
| ER5.2 | Unavailability of the supplier and delivery risk assessment service | Decisions may be made without the expected risk information. | A |
| ER5.3 | Disclosure of supplier contracts and commercial conditions | Loss of negotiating power and competitive advantage. | C |
 
### 4.6 EA6 – Business and Historical Data
 
| ID | Feared Event | Business impact | CIA |
|---|---|---|---|
| ER6.1 | Unauthorized or erroneous corruption of business and historical data | Unreliable analyses, forecasts, and business decisions. | I |
| ER6.2 | Unauthorized disclosure of customer or supplier data | Loss of trust and potential legal or regulatory consequences, subject to applicable legal assessment. | C |
| ER6.3 | Unavailability of the data warehouse | Interruption of analytical activities and AI model training. | A |
| ER6.4 | Irrecoverable loss of historical business data | Loss of organizational history and inability to use affected records for analysis or model development. | A |
 
ER6.3 concerns access to the data-warehouse service; ER6.4 concerns permanent loss of underlying historical records.
 
### 4.7 EA7 – AI Models and Training Data
 
| ID | Feared Event | Business impact | CIA |
|---|---|---|---|
| ER7.1 | Biased or poisoned AI models | Systematically inaccurate recommendations and business decisions. | I |
| ER7.2 | Unauthorized extraction or disclosure of proprietary AI models | Loss of intellectual property and competitive advantage, if model access or exposure makes extraction possible. | C |
| ER7.3 | Reconstruction of training data through model inversion | Disclosure of sensitive or personal information, if the model and its interfaces are susceptible to this technique. | C |
| ER7.4 | Undetected model drift | Gradual degradation of model performance may remain unnoticed and lead to increasingly unreliable recommendations. | To be validated |
 
ER7.4 is retained as a model-performance and operational concern. Its CIA classification requires an explicit project definition linking model-behaviour integrity to the classification used in this study.
 
### 4.8 EA8 – Decision Traceability and Auditability
 
| ID | Feared Event | Business impact | CIA |
|---|---|---|---|
| ER8.1 | Unauthorized modification of decision and activity logs | Loss of reliable audit evidence and inability to establish what actions or decisions occurred. | I |
| ER8.2 | Failure to record user overrides and their reasons | Lack of accountability and difficulty establishing responsibility following an incident. | I |
| ER8.3 | Unauthorized access to logs | Disclosure of sensitive operational and decision-related information. | C |
| ER8.4 | Loss or unavailability of decision and activity logs | Inability to review decisions or provide records required for an audit or investigation. | A |
 
---
 
## 5. Determine the Security Baseline
 
The security baseline below lists the reference measures that apply to the AI-SCMIS, with the standard or law each one comes from.
 
| Reference | Measure |
| --- | --- |
| Law 18-07 | Personal data limited to what is necessary |
| ISO 27090 (7.7, 7.8) | Malicious input filtering, request throttling |
| ISO 27090 (5.5, 5.6, 5.7) | AI supply chain tracing, threat modelling, red teaming |
| ISO 42001, ISO 27090 (5.2, 7.4) | Model registry with versions and owners, drift monitoring, rollback |
| ISO 27002, ANSSI guide | Backup and recovery |
| ISO 27002, ISO 27090 (7.5) | Logging of user activity, recommendations, approvals and overrides |
| ISO 27002, ISO 27090 (5.3) | Role-based access, least privilege, approval of high-impact actions |
 
---
