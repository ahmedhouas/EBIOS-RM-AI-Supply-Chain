# Workshop 1 – Review of Identified Issues and Decisions

**Project:** AI-Enabled Supply Chain Management Information System (AI-SCMIS)  
**Framework:** EBIOS Risk Manager  
**Date:** 06 November 2026  
**Purpose:** Record the issues identified during the review of Workshop 1 documents and the decisions taken before preparing the final report.

---

## 1. Purpose and Scope of This Review

This document consolidates the review findings and decisions concerning the preparation of the Workshop 1 report.

The review focuses on the following elements:

- Study scope.
- CIA and DAD classification.
- Identification of Essential Assets and their associated feared events.
- Security foundation.
- Content to be retained or excluded from the final report.

The Supporting Assets and Asset Owners sections are not reconsidered in this review.

## 2. Decisions Taken

| Subject | Decision |
|---|---|
| Study scope | Keep the current scope without modification. |
| CIA and DAD classification | Keep the current classification document. The recommendations identified during the review will be communicated separately. |
| BE4 name | Change the name to **Anomaly Detection and Fraud Indicators**. |
| Supporting Assets | Exclude this part from the current review. |
| Asset Owners | Exclude this part from the current review. |
| Cross-matrix | Remove the cross-matrix from the final report. |
| Dangerous-event analysis | Exclude its scope and detailed analysis from the final report. Retain it as reference material for Workshop 2. |
| Security foundation | Remove the current status and gap/justification presentation. |
| Final report preparation | Proceed after completing the remaining corrections listed in this document. |

## 3. Identification of Feared Events – Issues and Required Corrections

The Identification of Feared Events section requires several adjustments before it can be included in the final report.

The following list contains only the changes that need to be made.

### 3.1. Essential Asset Naming

- [ ] Rename **BE4 – Anomaly and Fraud Detection** to **BE4 – Anomaly Detection and Fraud Indicators**.
- [ ] Ensure that the new name is used consistently throughout the feared-events document.
- [ ] Update references to BE4 wherever the old name appears.

### 3.2. Feared Events Associated with BE1 – Demand Forecasting

- [ ] Review **ER1.4 – Lack of model version traceability**.
- [ ] Clarify its scope so that it concerns the traceability of forecasting model versions specifically, and does not duplicate the broader decision traceability covered by BE8.

### 3.3. Feared Events Associated with BE2 – Replenishment and Inventory Management

- [ ] Review **ER2.4 – Unauthorized safety-stock threshold modification**.
- [ ] Confirm that the system actually includes safety-stock threshold management.
- [ ] If this functionality is not established in the system description, revise or remove the feared event.

### 3.4. Feared Events Associated with BE3 – Order and Delivery Management

- [ ] Separate **ER3.1 – Loss or unauthorized modification of orders** into distinct feared events, because loss of orders and unauthorized modification represent different consequences.
- [ ] Review **ER3.4 – Unexpected delivery delays**.
- [ ] Clarify the business consequence of delivery delays and avoid classifying a physical delivery delay automatically as an information-system availability failure.

### 3.5. Feared Events Associated with BE4 – Anomaly Detection and Fraud Indicators

- [ ] Review **ER4.1 – Failure to detect actual fraudulent activities**.
- [ ] Ensure that the wording does not imply that the system proves or directly identifies fraud. The system detects anomalies or suspicious indicators.
- [ ] Review **ER4.2 – Excessive false positives**.
- [ ] Clarify the actual consequence of excessive false alerts and reconsider its classification under Availability.
- [ ] Review **ER4.3 – Circumvention of fraud detection model**.
- [ ] Clarify what the circumvention would cause for the organization and how it affects the Essential Asset.

### 3.6. Feared Events Associated with BE6 – Business and Historical Data

- [ ] Separate **ER6.1 – Corruption or loss of historical data** into distinct feared events, distinguishing data integrity from data availability.

### 3.7. Feared Events Associated with BE7 – AI Models and Training Data

- [ ] Review **ER7.2 – Theft of proprietary models** and clarify the conditions under which model theft is possible.
- [ ] Review **ER7.3 – Reconstruction of training data via model inversion** and clarify that this event depends on the model's exposure and technical characteristics.
- [ ] Review **ER7.4 – Undetected model drift** and clarify why it is classified as an Integrity-related feared event.

### 3.8. General Consistency

- [ ] Check that each feared event describes a clear negative consequence for the organization.
- [ ] Check that each feared event is associated with the correct Essential Asset.
- [ ] Remove or revise duplicate feared events.
- [ ] Ensure that the CIA classification assigned to each feared event corresponds to the consequence being described.
- [ ] Ensure that the terminology is consistent throughout the document.
- [ ] Check that all Essential Asset identifiers (BE1–BE8) and feared-event identifiers (ERx.x) are consistent.

## 4. Security Foundation – Required Changes

The current security foundation document contains a status and gap/justification analysis.

The decision is to remove this presentation from the final report.

Required actions:

- [ ] Remove the Applied / Applied with restrictions / Not applied status column.
- [ ] Remove the gap and justification analysis associated with these statuses.
- [ ] Do not present unmentioned security measures as confirmed absent from the system.
- [ ] Retain only the security-related information that is relevant to the final report structure and supported by the case-study documentation.
- [ ] Ensure that the security foundation section does not imply that the ISSP has already been established or that future risk-treatment decisions have already been implemented.

## 5. Content Excluded from the Final Report

The following elements will not appear as detailed sections in the final Workshop 1 report.

### 5.1. Cross-Matrix

The dangerous-event and Essential Asset cross-matrix will be removed from the final report.

It may remain in the working documents as supporting material, but it should not be included in the final report.

### 5.2. Dangerous-Event Analysis

The detailed scope and analysis of dangerous events will be excluded from the final report.

This material will be retained as reference material for Workshop 2, where it can support the continuation of the risk analysis.

The exclusion does not mean that the existing material is considered invalid. It means that it will be handled separately from the Workshop 1 final report.

## 6. Final Report Preparation – Agreed Structure

The final Workshop 1 report will follow the structure defined in the Workshop 1 briefing document, with the agreed terminology and exclusions.

1. **Define the Study Scope**
   - Strategic Scope
   - Operational Scope

2. **Define CIA Classes**

3. **Define the Business and Technical Perimeter**
   - Essential Assets
   - Supporting Assets

4. **Identify Feared Events**

5. **Determine the Security Foundation**

The section titled **Define the Study Framework** will not be included as a separate section.

## 7. Final Checklist Before Report Drafting

- [ ] Apply the BE4 name change consistently.
- [ ] Correct the feared events identified in Section 3.
- [ ] Verify the wording and CIA classification of all feared events.
- [ ] Check the consistency of Essential Asset and feared-event identifiers.
- [ ] Remove the cross-matrix from the final report material.
- [ ] Move the dangerous-event analysis to the Workshop 2 reference material.
- [ ] Remove the status and gap/justification analysis from the security foundation.
- [ ] Confirm that the CIA/DAD recommendations have been communicated separately.
- [ ] Prepare the final Workshop 1 report using the agreed structure.

## 8. Conclusion

The review has established the decisions necessary to prepare the final Workshop 1 report.

The study scope remains unchanged. The CIA/DAD classification is retained, with recommendations to be communicated separately. The BE4 Essential Asset will be renamed, and the feared events will be corrected according to the checklist in this document.

The Supporting Assets and Asset Owners sections are not part of this review. The cross-matrix and detailed dangerous-event analysis will be excluded from the final report and retained as supporting material for subsequent work, particularly Workshop 2. The security foundation will also be revised by removing the current status and gap/justification analysis.

**Once the remaining corrections to the feared events and security foundation have been completed, the Workshop 1 material will be ready for final report drafting.**
