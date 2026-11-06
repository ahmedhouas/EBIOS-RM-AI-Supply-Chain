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
 
The class definitions above reproduce the project's classification scale. This report does not assign a class to each Essential Asset because the reviewed asset inventory does not contain those assignments. The project-specific classification recommendations are being handled separately.
 
---
 
## 3. Define the Business and Technical Perimeter
 
### 3.1 Essential Assets
 
Essential Assets are the processes and information whose compromise could seriously harm the organization. The project inventory identifies eight Essential Assets.
 
| ID | Essential Asset | Type | Description |
|---|---|---|---|
| BE1 | Demand forecasting | Process | Machine-learning models estimate future demand for products and warehouses using historical sales, seasonality, promotions, lead times, and calendar effects. The forecasts support downstream replenishment decisions. |
| BE2 | Replenishment and inventory management | Process | Determines what quantity to order and when, using forecasts, current stock, goods already on order, supplier lead times, safety-stock requirements, storage capacity, and budget constraints. Large or exceptional orders require human approval. |
| BE3 | Order and delivery management | Process | Covers customer-order reception, warehouse picking, dispatch, delivery through contracted carriers, shipment tracking, and customer/service-centre notifications. |
| BE4 | Anomaly Detection and Fraud Indicators | Process | Identifies unusual patterns such as abnormal order quantities, unexpected stock reductions, repeated order changes, or duplicate invoices. An alert is an indicator for investigation, not proof of fraud; authorized staff verify it. |
| BE5 | Supplier and delivery risk assessment | Process | Estimates supplier-delay and late-delivery risks using historical lead times, shipment events, and supplier performance, and supports consideration of alternatives. |
| BE6 | Business and historical data | Information | Includes orders, point-of-sale history, product catalogues, stock levels, warehouse receipts, purchase orders, supplier lead times, carrier tracking events, and approved external indicators. It also includes limited personal data needed for fulfilment and customer service. |
| BE7 | AI models and training data | Information | Includes trained forecasting, optimization, anomaly-detection, and supplier-risk models; their versions, evaluation results, and approval status; and the datasets used to train them. |
| BE8 | Decision traceability and auditability | Information | Includes records of user activity, recommendation details, model version and input data, approvals, overrides and their reasons, and resulting actions, enabling decisions to be traced and reviewed. |
 
### 3.2 Supporting Assets
 
Supporting Assets are the elements on which Essential Assets depend. The project inventory identifies the following supporting-asset categories.
 
| Supporting Asset | Role in the system |
|---|---|
| ERP, WMS, TMS and inventory system | Support planning, procurement, finance, warehouse operations, routing, carrier management, and stock information. |
| Sales platform and order API | Receive customer orders and transmit them to operational systems. |
| Integration service (ETL/ELT, APIs) | Receives and validates records, standardizes units and dates, matches identifiers, and flags data-quality issues. |
| Operational database and data warehouse (data lake) | Store current operational information and historical records used for analytics and model training. |
| AI services | Provide demand forecasting, inventory recommendations, anomaly detection, supplier-risk estimation, and delivery-time prediction. |
| Model registry and training pipeline | Record model versions and evaluation information and support training, validation, monitoring, retraining, and rollback. |
| Dashboards and logging system | Present role-specific recommendations and alerts and record user activity, approvals, and overrides. |
| IoT sensors, barcode scanners, warehouse terminals | Collect stock movement, location, and delivery-related information through devices used in warehouses and shipping operations. |
| Server, cloud and network infrastructure | Host and connect the applications, databases, and models. |
| Privileged users | Users with extended access to data, models, administration, or approval functions. |
| Suppliers, carriers and external sources | Provide supplier, carrier, shipment-tracking, and approved external information used by the system. |
 
The supporting-asset list includes technical systems, devices, users, and external organizations. The inventory describes the categories and their roles; detailed dependency mapping is not included in this report.
 
---
 
## 4. Identify Feared Events
 
A Feared Event is a negative consequence for the organization resulting from compromise of an Essential Asset. The events below are associated with the CIA property affected.
 
### 4.1 BE1 – Demand Forecasting
 
| ID | Feared Event | Business impact | CIA |
|---|---|---|---|
| ER1.1 | Inaccurate or biased demand forecasts | Overstocking, stockouts, financial losses, and inadequate planning. | I |
| ER1.2 | Unavailability of the forecasting service | Disruption of forecasting activities and reduced ability to plan replenishment. | A |
| ER1.3 | Disclosure of historical sales and strategic data | Loss of competitive advantage. | C |
| ER1.4 | Inability to identify the model version used to generate a forecast | Inability to reproduce, review, or explain a specific forecast and related decisions. | I |
 
ER1.4 is limited to forecasting-model version traceability. General decision and activity traceability is addressed under BE8.
 
### 4.2 BE2 – Replenishment and Inventory Management
 
| ID | Feared Event | Business impact | CIA |
|---|---|---|---|
| ER2.1 | Incorrect replenishment recommendations | Capital immobilization, excessive inventory, or stockouts. | I |
| ER2.2 | Circumvention of human validation for high-value orders | Unauthorized financial commitments and potential internal misuse. | I |
| ER2.3 | Unavailability of the inventory optimization service | Disruption of purchasing operations and supply-chain activities. | A |
| ER2.4 | Unauthorized modification of safety-stock requirements or thresholds | Unexpected stockouts or excessive storage costs. | I |
 
The case study includes safety-stock requirements in replenishment calculations. The detailed threshold-management process is not specified.
 
### 4.3 BE3 – Order and Delivery Management
 
| ID | Feared Event | Business impact | CIA |
|---|---|---|---|
| ER3.1 | Loss or unavailability of customer-order records | Orders may not be processed or fulfilled, causing potential revenue loss, disputes, and reputational damage. | A |
| ER3.2 | Unavailability of the sales platform or order API | Interruption of order processing and potential revenue losses. | A |
| ER3.3 | Unauthorized disclosure of customers' personal data | Loss of customer trust and potential legal or regulatory consequences, subject to applicable legal assessment. | C |
| ER3.4 | Failure to deliver orders within the expected timeframe | Customer dissatisfaction, contractual consequences, and disruption of the delivery service. | A |
| ER3.5 | Unauthorized modification of customer-order information | Incorrect order fulfilment, disputes, financial loss, and reputational damage. | I |
 
ER3.4 concerns the timeliness of the business delivery service and does not automatically indicate an IT system outage.
 
### 4.4 BE4 – Anomaly Detection and Fraud Indicators
 
| ID | Feared Event | Business impact | CIA |
|---|---|---|---|
| ER4.1 | Failure to identify abnormal or suspicious activity (false negatives) | Suspicious activity may remain undetected and uninvestigated, potentially resulting in financial or inventory losses. | I |
| ER4.2 | Excessive false-positive alerts | Alert fatigue, increased investigation workload, delayed review of relevant alerts, and reduced confidence in detection results. | I |
| ER4.3 | Evasion or circumvention of anomaly-detection controls | Relevant abnormal patterns may not be flagged, allowing potentially harmful activity to remain undetected. | I |
 
Anomaly alerts are signals for investigation and are not proof that fraud has occurred.
 
### 4.5 BE5 – Supplier and Delivery Risk Assessment
 
| ID | Feared Event | Business impact | CIA |
|---|---|---|---|
| ER5.1 | Inaccurate supplier risk assessment | Unexpected delays and supply-chain disruptions. | I |
| ER5.2 | Unavailability of the supplier and delivery risk assessment service | Decisions may be made without the expected risk information. | A |
| ER5.3 | Disclosure of supplier contracts and commercial conditions | Loss of negotiating power and competitive advantage. | C |
 
### 4.6 BE6 – Business and Historical Data
 
| ID | Feared Event | Business impact | CIA |
|---|---|---|---|
| ER6.1 | Unauthorized or erroneous corruption of business and historical data | Unreliable analyses, forecasts, and business decisions. | I |
| ER6.2 | Unauthorized disclosure of customer or supplier data | Loss of trust and potential legal or regulatory consequences, subject to applicable legal assessment. | C |
| ER6.3 | Unavailability of the data warehouse | Interruption of analytical activities and AI model training. | A |
| ER6.4 | Irrecoverable loss of historical business data | Loss of organizational history and inability to use affected records for analysis or model development. | A |
 
ER6.3 concerns access to the data-warehouse service; ER6.4 concerns permanent loss of underlying historical records.
 
### 4.7 BE7 – AI Models and Training Data
 
| ID | Feared Event | Business impact | CIA |
|---|---|---|---|
| ER7.1 | Biased or poisoned AI models | Systematically inaccurate recommendations and business decisions. | I |
| ER7.2 | Unauthorized extraction or disclosure of proprietary AI models | Loss of intellectual property and competitive advantage, if model access or exposure makes extraction possible. | C |
| ER7.3 | Reconstruction of training data through model inversion | Disclosure of sensitive or personal information, if the model and its interfaces are susceptible to this technique. | C |
| ER7.4 | Undetected model drift | Gradual degradation of model performance may remain unnoticed and lead to increasingly unreliable recommendations. | To be validated |
 
ER7.4 is retained as a model-performance and operational concern. Its CIA classification requires an explicit project definition linking model-behaviour integrity to the classification used in this study.
 
### 4.8 BE8 – Decision Traceability and Auditability
 
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
