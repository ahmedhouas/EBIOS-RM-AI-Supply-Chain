# EBIOS-RM Risk Analysis – AI-Enabled Supply Chain Management Information System

## 1. Project Overview

This project aims to conduct an information security risk analysis of an **AI-Enabled Supply Chain Management Information System (AI-SCMIS)** using the **EBIOS Risk Manager (EBIOS-RM)** methodology.

The case study describes a fictional distribution company that supplies spare parts and equipment to several regional warehouses and customer service centres. The organisation relies on an integrated information system combining operational data, external services and artificial intelligence to improve supply chain planning, inventory management and delivery operations.

The project follows the five EBIOS-RM workshops to identify, analyse and evaluate information security risks. Based on the results, a consolidated risk analysis report will be produced, followed by updates and reductions of the organisation's Information System Security Policy (ISSP) and Business Continuity Plan (BCP).

## 2. Case Study: AI-Enabled Supply Chain Management Information System

### 2.1 System Description

The AI-SCMIS integrates operational information and AI-based services to support supply chain activities, including:

- Demand forecasting and seasonal variation prediction.
- Inventory optimisation and replenishment recommendations.
- Detection of abnormal orders and stock movements.
- Supplier risk assessment.
- Delivery-time prediction and logistics risk management.
- Management dashboards, notifications and reporting.

The system aims to improve product availability and delivery reliability while reducing excess inventory, transportation costs and operational disruptions.

### 2.2 System Architecture

The system is organised into five main layers:

| Layer | Description |
|---|---|
| Data Sources Layer | Collects information from enterprise systems, IoT devices, suppliers, customers and external data sources. |
| Ingestion & Integration Layer | Handles data collection, integration, validation, cleaning and storage. |
| AI & Analytics Layer | Performs demand forecasting, anomaly detection, supplier risk assessment and inventory optimisation. |
| Application Layer | Provides supply chain planning, inventory management, logistics, supplier management and reporting services. |
| User Layer | Supports interaction between supply chain managers, operational teams, suppliers and customers. |

### 2.3 AI Workflow

The system operates through a connected multi-stage AI workflow:

1. **Data Collection and Preparation:** Collecting, validating, cleaning and integrating operational data.
2. **AI-Based Demand Forecasting:** Predicting future product demand using historical information and contextual indicators.
3. **Inventory Optimisation and Replenishment:** Recommending purchase quantities and replenishment timing.
4. **Anomaly and Fraud-Indicator Detection:** Identifying unusual transactions, stock movements and order patterns.
5. **Supplier and Delivery Risk Prediction:** Estimating supplier delays and delivery risks.
6. **Human Decision, Execution and Feedback:** Allowing authorised employees to review, approve, modify or reject AI recommendations and returning operational outcomes for performance monitoring and improvement.

Human oversight, traceability, controlled access and model monitoring are important characteristics of the system.

## 3. Project Objectives

The main objectives are:

- Understand the organisation's information system, business processes and operational environment.
- Identify critical business values and supporting assets.
- Identify relevant sources of risk and their objectives.
- Develop strategic and operational risk scenarios.
- Evaluate and prioritise information security risks.
- Define appropriate risk treatment measures.
- Produce a formal risk analysis report.
- Update and reduce the existing ISSP based on the risk analysis results.
- Update and reduce the existing BCP according to the identified risks and continuity requirements.

## 4. Methodology – EBIOS Risk Manager

The project follows the five-workshop EBIOS-RM methodology.

| Workshop | Title | Main Objective |
|---|---|---|
| Workshop 1 | Framing & Security Base | Define the scope, business values, supporting assets and security baseline. |
| Workshop 2 | Sources of Risk | Identify sources of risk, their motivations, capabilities and risk objectives. |
| Workshop 3 | Strategic Scenarios | Develop scenarios describing how sources of risk could affect business values. |
| Workshop 4 | Operational Scenarios | Analyse technical attack paths, vulnerabilities and operational scenarios. |
| Workshop 5 | Risk Treatment | Evaluate risks, select treatment strategies and define security measures. |

Each workshop includes preparation, evidence collection, stakeholder engagement, a working session, documentation and validation.

## 5. Project Deliverables

The project is expected to produce the following deliverables:

### 5.1 EBIOS-RM Workshop Outputs
Documentation and analysis produced during the five workshops, including assets, sources of risk, strategic scenarios, operational scenarios and risk treatment decisions.

### 5.2 Consolidated Risk Analysis Report
A formal report presenting the methodology, organisational context, identified risks, scenarios, risk evaluation, treatment decisions and recommendations.

### 5.3 Updated/Reduced Information System Security Policy (ISSP)
A reviewed and updated version of the existing ISSP, reflecting the identified risks and selected security measures while removing outdated or redundant content.

### 5.4 Updated/Reduced Business Continuity Plan (BCP)
A reviewed and updated version of the existing BCP, reflecting critical activities, disruption scenarios, recovery requirements and continuity measures.

## 6. Project Organisation

The project is conducted by a team of 10 members:

- **8 technical and coordination members:** Responsible for project coordination, EBIOS-RM analysis, information security, technical assessment, business processes, governance and business continuity.
- **2 document reductors/editors:** Responsible for consolidating workshop outputs, drafting the risk analysis report and updating/reducing the ISSP and BCP.

The two editors coordinate documentation throughout the five workshops to ensure consistency, traceability and quality.

## 7. Repository Structure

The repository is organised according to the different project phases.

| Directory | Purpose |
|---|---|
| `01_Project_Management/` | Project planning, task allocation, meeting reports and schedules. |
| `02_Preparation/` | Case study documentation, stakeholder information, evidence and initial asset classification. |
| `03_EBIOS_RM_Workshops/` | Preparation, analysis and final outputs of the five workshops. |
| `04_Risk_Analysis_Report/` | Drafting, reviewing and finalising the consolidated risk analysis report. |
| `05_ISSP/` | Existing ISSP, analysis, drafts, reviews and final updated document. |
| `06_BCP/` | Existing BCP, analysis, drafts, reviews and final updated document. |
| `07_Quality_Assurance/` | Quality checklists, review reports, approvals and traceability. |
| `08_Final_Deliverables/` | Consolidated and approved project deliverables. |
| `09_References/` | EBIOS-RM methodology, standards and supporting references. |

## 8. Version Control and Collaboration

GitHub is used as the central version control and document collaboration platform throughout the project.

The collaboration workflow follows these principles:

1. The `main` branch contains approved project documents.
2. Team members create dedicated branches for their tasks.
3. Changes are committed with descriptive messages.
4. Pull Requests are used to submit and review modifications.
5. Relevant analysts validate technical content.
6. The designated editors coordinate document consolidation and final versions.
7. Approved changes are merged into `main`.

### Branch Naming Convention

Examples:

- `docs/project-planning`
- `docs/workshop-1`
- `docs/workshop-2`
- `docs/workshop-3`
- `docs/workshop-4`
- `docs/workshop-5`
- `docs/risk-report`
- `docs/issp-update`
- `docs/bcp-update`

## 9. Security and Documentation Management

Since this project involves information security assessments, technical architecture and potential vulnerabilities, repository access must be restricted to authorised team members.

The following rules apply:

- Keep the repository private.
- Do not commit passwords, credentials, private keys or access tokens.
- Store only authorised project evidence.
- Maintain document traceability and version history.
- Validate sensitive technical information before publishing it in shared documents.
- Keep approved final documents distinguishable from working drafts.

## 10. References and Supporting Materials

The project uses the provided AI-SCMIS case study as its primary system description.

Additional methodological and technical references include:

- EBIOS Risk Manager methodology.
- Relevant information security standards.
- ISO/IEC 27090:2026, concerning cybersecurity and artificial intelligence security threats and compromises, as a suggested supporting reference in the case study.

Further references will be documented in `09_References/`.

---

**Project:** EBIOS-RM Risk Analysis – AI-Enabled Supply Chain Management Information System

**Methodology:** EBIOS Risk Manager – Five Workshops

**Team:** 10 Members (8 Technical/Coordination Members + 2 Document Editors)

**Main Outputs:** EBIOS-RM Workshop Reports, Risk Analysis Report, Updated ISSP and Updated BCP.
