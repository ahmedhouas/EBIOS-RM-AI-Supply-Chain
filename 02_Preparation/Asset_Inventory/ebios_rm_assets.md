# Essential Assets

## Essential and Supporting Assets

Essential assets are the processes and information whose loss or compromise would seriously harm the organization.

| Essential asset | Type | Description | Owner |
| :--- | :--- | :--- | :--- |
| Demand forecasting | Process | Machine learning models estimate future demand for each product and warehouse over a planning horizon, using historical sales, seasonality, promotions, lead times and calendar effects. It replaces manual, static estimation and drives all downstream replenishment decisions. | Planning manager |
| Replenishment and inventory management | Process | Calculates what quantity to order and when, by combining the demand forecast with current stock, goods already on order, supplier lead times, safety stock, storage capacity and budget constraints. Large or exceptional orders require human approval. | Procurement manager |
| Order and delivery management | Process | Covers the full path from the reception of a customer order to warehouse picking, dispatch and delivery through contracted carriers, including shipment tracking and notifications to customers and service centres. | Logistics manager |
| Anomaly and fraud detection | Process | Identifies unusual patterns such as abnormal order quantities, unexpected stock reductions, repeated order changes or duplicate invoices. An alert is a signal for investigation, not proof of fraud, and is verified by authorized staff. | Control manager |
| Supplier and delivery risk assessment | Process | Estimates the probability of supplier delay or late delivery from historical lead times, shipment events and supplier performance, and proposes alternatives such as contacting the supplier, reserving alternative stock or comparing approved carriers. | Purchasing manager |
| Business and historical data | Information | Orders, point-of-sale history, product catalogues, stock levels, warehouse receipts, purchase orders, supplier lead times, carrier tracking events and approved external indicators (weather, holidays). Includes the limited personal data needed for fulfilment and customer service. | Data owners |
| AI models and training data | Information | The trained models (forecasting, optimization, anomaly detection, supplier risk), their versions, evaluation results and approval status, and the datasets used to train them. They are the intellectual property of the organization and the basis of every AI recommendation. | Data / AI manager |
| Decision traceability and auditability | Information | Logs of user activity, recommendation details, the model version and input data behind each recommendation, approvals, overrides with their reasons and the resulting actions, so that every decision can be traced and audited. | CISO/governance |

---

# Supporting Assets

Supporting assets are the elements on which the essential assets rely: they are what attacks target.

| Supporting asset | Description |
| :--- | :--- |
| ERP, WMS, TMS and inventory system | Core business applications: the ERP for planning, procurement and finance; the WMS for warehouse operations such as put-away and picking; the TMS for routing and carrier management; and the inventory system for on-hand, in-transit and inbound stock. |
| Sales platform and order API | The platform through which customer orders are received and the API that transmits them to the operational systems. It is the main entry point of customer data. |
| Integration service (ETL/ELT, APIs) | Receives and validates records, checks required fields, standardizes units and dates, matches product and supplier identifiers, and flags duplicates, missing values and implausible quantities before the data is used by the models. |
| Operational database and data warehouse (data lake) | The operational database holds current orders and stock. The historical data store retains approved records for analytics and model training, with data lineage so that model inputs can be traced to their source. |
| AI services | Separate services for demand forecasting, inventory recommendations, anomaly detection, supplier risk estimation and delivery-time prediction, running in the live environment on new data. |
| Model registry and training pipeline | Records model versions, evaluation results, owners, approval status and deployment dates. Supports controlled training, validation, monitoring for drift, retraining and rollback to a validated version. |
| Dashboards and logging system | Role-specific dashboards (warehouse, procurement, logistics, management) that present recommendations and alerts, and the logs that record user activity, approvals and overrides. |
| IoT sensors, barcode scanners, warehouse terminals | Devices on shipping containers and in warehouses (sensors, RFID, GPS, barcode scanners) that report stock movements, locations and delivery events in real time. |
| Server, cloud and network infrastructure | Servers, cloud hosting, storage and network links that run all applications, databases and models, and connect the organization to its partners. |
| Privileged users | Administrators, data scientists, data owners and procurement staff with extended access rights to data, models and approval functions. |
| Suppliers, carriers and external sources | Supplier portals and the tracking systems of contracted carriers, plus external feeds such as market trends, weather and public holidays that provide inputs to the system. |