# 1 Scope of Study

## 1.1 Strategic Scope

The system under study is an AI-enabled Supply Chain Management Information System. Its principal mission is to support supply chain management through dynamic machine learning models that replace manual, static estimation methods. It has an enterprise-wide scope. This section establishes what the system does, and therefore what requires protection, before analyzing potential attack vectors or defensive measures.

The system's fundamental business value lies in turning large volumes of internal and external data into traceable, data-supported decisions for human managers. The objectives considered essential in this study are as follows:

* Predicting product demand and seasonal variations.
* Recommending replenishment quantities and the timing of replenishment orders.
* Identifying abnormal orders and supplier risks in real time.
* Anticipating delivery delays and formulating alternative logistical plans.
* Providing human managers with traceable, data-supported decisions.

## 1.2 Operational Scope

This study focuses on the system's operating workflow, whose compromise could significantly affect supply chain activity. The workflow has seven stages:

* **Data collection:** The system draws data from internal enterprise systems, IoT sensors on shipping containers, and supplier portals. It also uses external feeds, including market trends and weather data. The source describes this input as large in volume and varied in character.
* **Data processing:** Collected data is cleaned, standardized, and integrated.
* **AI model training:** Machine learning models are built and trained to recognize patterns, such as those used to forecast demand or detect anomalies in supplier behavior.
* **Inference and prediction:** Trained models are applied to new, real-time data in the live environment to generate insights.
* **Decision making:** Insights are presented to human users for action.
* **Execution:** Decisions are carried out, for example by placing purchase orders or routing trucks.
* **Continuous improvement:** The system monitors outcomes to refine and retrain its models.

The workflow forms a loop: outcomes observed after execution feed back into model refinement and retraining. Human users are involved at the decision-making stage. The source does not specify the degree of automation at the execution stage, which would need clarification in any later risk assessment. The source also provides no quantitative performance data, technical specifications, vendor or deployment details, or security analysis. These matters are outside the scope of this section.

2