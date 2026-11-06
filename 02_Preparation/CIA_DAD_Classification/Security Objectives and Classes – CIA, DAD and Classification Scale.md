# Security Objectives and Security Classes: CIA, DAD and Classification Scale

Reference sheet: definitions of the CIA triad, the DAD triad and the security classes used in this project.

## 1. Security objectives: the CIA triad

Information security aims to preserve three basic properties of information, known as the CIA triad. This is also how the ISO/IEC 27000 family of standards defines information security.

| Property | Definition | Question it answers | Example in the AI-SCMIS | 
| --- | --- | --- | --- | 
| Confidentiality | Information is available only to authorised persons, entities and processes | Who is allowed to see it? | Customer personal data, supplier contracts and prices | 
| Integrity | Information and systems stay accurate, complete and unaltered, except through authorised actions | Is it correct and unmodified? | Stock records, forecasts, model files | 
| Availability | Information and services are accessible and usable on demand by authorised users | Can it be used when needed? | ERP and WMS, order processing | 

## 2. The opposite of CIA: the DAD triad (CIA $\neq$ DAD)

CIA $\neq$ DAD. DAD describes what happens when security fails: the three types of compromise, each one attacking one CIA property.

| CIA property lost | DAD term | Meaning | Example | 
| --- | --- | --- | --- | 
| Confidentiality | Disclosure | Information is revealed to an unauthorised party | Leak of customer data | 
| Integrity | Alteration | Information is modified without authorisation or by error | Poisoned training data causing wrong forecasts | 
| Availability | Destruction (also called Denial) | Information or service is erased, lost or made inaccessible | Ransomware encrypting the ERP | 

## 3. Security classes

In this project, classes are defined for each security objective. A higher number means a stronger protection requirement.

### 3.1 Confidentiality classes

| Class | Level | Meaning | Typical protection | 
| --- | --- | --- | --- | 
| C1 | Public | Information can be freely disclosed; disclosure causes no harm | No specific protection | 
| C2 | Secret | Information is reserved for the organisation’s authorised staff; disclosure would harm the organisation | Access control, need-to-know | 
| C3 | Confidential | Highest level; disclosure would cause serious harm | Named access only, encryption, access logging | 

### 3.2 Integrity classes

| Class | Level | Meaning | Typical protection | 
| --- | --- | --- | --- | 
| I1 | Normal | An error or alteration has limited consequences and can be corrected | Standard checks and backups | 
| I2 | Intact | Information must be exact and complete; any alteration is unacceptable and must be prevented or detected | Integrity checks (hashes, signatures), logging, dual approval | 

### 3.3 Availability classes

| Class | Level | Meaning | 
| --- | --- | --- | 
| D1 | Normal | Long interruptions are acceptable | 
| D2 | Moderate | Interruptions are tolerated for a limited time | 
| D3 | High | Interruptions are tolerated only for a short time | 
| D4 | Critical | The service must be available almost continuously; any interruption has a major impact | 
