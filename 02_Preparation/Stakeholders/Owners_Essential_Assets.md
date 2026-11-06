# Essential Assets - Owners

Owners, associated essential assets and descriptions extracted from source documentation.

| Owner | Essential asset | Description |
| ----- | ----- | ----- |
| Planning manager | Demand forecasting | Machine learning models estimate future demand for each product and warehouse over a planning horizon, using historical sales, seasonality, promotions, lead times and calendar effects. It replaces manual, static estimation and drives all downstream replenishment decisions. |
| Procurement manager | Replenishment and inventory management | Calculates what quantity to order and when, by combining the demand forecast with current stock, goods already on order, supplier lead times, safety stock, storage capacity and budget constraints. Large or exceptional orders require human approval. |
| Logistics manager | Order and delivery management | Covers the full path from the reception of a customer order to warehouse picking, dispatch and delivery through contracted carriers, including shipment tracking and notifications to customers and service centres. |
| Control manager | Anomaly and fraud detection | Identifies unusual patterns such as abnormal order quantities, unexpected stock reductions, repeated order changes or duplicate invoices. An alert is a signal for investigation, not proof of fraud, and is verified by authorized staff. |
| Purchasing manager | Supplier and delivery risk assessment | Estimates the probability of supplier delay or late delivery from historical lead times, shipment events and supplier performance, and proposes alternatives such as contacting the supplier, reserving alternative stock or comparing approved carriers. |
| Data owners | Business and historical data | Orders, point-of-sale history, product catalogues, stock levels, warehouse receipts, purchase orders, supplier lead times, carrier tracking events and approved external indicators (weather, holidays). Includes the limited personal data needed for fulfilment and customer service. |
| Data / AI manager | AI models and training data | The trained models (forecasting, optimization, anomaly detection, supplier risk), their versions, evaluation results and approval status, and the datasets used to train them. They are the intellectual property of the organization and the basis of every AI recommendation. |
| CISO/governance | Decision traceability and auditability | Logs of user activity, recommendation details, the model version and input data behind each recommendation, approvals, overrides with their reasons and the resulting actions, so that every decision can be traced and audited. |
