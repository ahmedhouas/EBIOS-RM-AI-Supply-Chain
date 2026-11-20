# Workshop 3 - Strategic Scenarios [draft]

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