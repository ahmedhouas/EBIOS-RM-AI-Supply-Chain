# 1. Security baseline

Baseline measures, application status and gaps.

| Reference | Measure | Status | Gap / justification |
| --- | --- | --- | --- |
| Law 18-07 | Personal data limited to what is necessary | Applied with restrictions | Retention periods and formalities with the national authority aren't described |
| ISO 27090 (7.7, 7.8) | Malicious input filtering, request throttling | Not applied | No malicious input filtering and no request throttling on the AI services. Risk: prompt injection (ED-IA7), evasion (ED-IA3), model extraction (ED-IA6) and model inversion (ED-IA5), leading to ER1.1, ER2.1, ER4.3, ER5.1, ER7.2 and ER7.3. Addressed in PSSI. |
| ISO 27090 (5.5, 5.6, 5.7) | AI supply chain tracing, threat modelling, red teaming | Not applied | No AI supply chain tracing, threat modelling or red teaming. Risk: data poisoning (ED-IA1) and direct model poisoning (ED-IA2) of the historical data, training pipeline, model registry and AI services, leading to ER1.1, ER2.1 and ER7.1. Addressed in PSSI. |
| ISO 42001, ISO 27090 (5.2, 7.4) | Model registry with versions and owners, drift monitoring, rollback | Applied | The model registry tracks each model’s versions, owners and approval status, and poorly performing models are retrained or rolled back. No major gap. |
| ISO 27002, ANSSI guide | Backup and recovery | Not applied | "Recoverability" is only a requirement, with no mechanism described; to be covered by the PCA |
| ISO 27002, ISO 27090 (7.5) | Logging of user activity, recommendations, approvals and overrides | Applied with restrictions | Model input/output logging and abuse detection aren't described |
| ISO 27002, ISO 27090 (5.3) | Role-based access, least privilege, approval of high-impact actions | Applied with restrictions | The description doesn't mention strong authentication or privileged-account management |

## EXPLAINING FOR WORKSHOP 2 MEMBERS AND OTHERS

Here is what each column of the table means:
* **Reference:** the standard or law the measure comes from, with the ISO 27090 clause number where relevant.
* **Measure:** one concrete security measure from that reference that applies to your system, for example role-based access or logging.
* **Status:** how far the system applies that measure today, based on the system description. It has three values:
  * **Applied:** the description shows the measure is in place.
  * **Applied with restrictions:** it is partly in place.
  * **Not applied:** the description doesn’t mention it.
* **Gap / justification:** the reason for the status. For “applied” it points to the section of the description that proves it. For “with restrictions” or “not applied” it names what is missing.

### NOTE!
Since the system is fictional, project description in pdfs is our only source about it, so a measure that isn’t described is treated as not in place. We state that as an assumption, for example the 2nd & 3rd line of the baseline table in justification columns, so either we ask the professor or we keep it like that.

From our project files (you can verify these). The ISO 27090 clause numbers come from the clause diagram in the project PDF:
* 5.2 is the AI governance programme.
* 5.3 is zero trust principles (the feelagile article says this includes least privilege).
* 5.5 to 5.7 are supply chain management, threat modelling and red teaming.
* 7.5 is logging and monitoring.
* 7.7 and 7.8 are malicious input detection and throttling model use.

ANSSI guide (ISO 27002, ANSSI guide reference) fits the method our project requires. EBIOS RM was created by ANSSI, the French national cybersecurity agency, so the guide comes from the same source as our methodology. Teams doing EBIOS RM commonly use it as their basic security reference.

It fits the legal side of our system. Law No. 18-07 is the Algerian law that protects people whose personal data is processed, and our system handles customer orders and delivery information. It is the only legal reference in the baseline, so it shows we considered Algerian law and not only international standards.