# Workshop 4 – Operational Scenarios
## Report Review and Assessment

### 1. General Assessment

The Workshop 4 report (*Operational Scenarios*) provides a solid foundation for the operational analysis of the AI-Enabled Supply Chain Management Information System (AI-SCMIS).

The document demonstrates a structured approach to decomposing strategic scenarios into operational attack paths, identifying associated vulnerabilities, describing attack sequences, and assessing their corresponding risk levels.

Overall, the report is well organized and contains the necessary elements to support the transition towards Workshop 5 (Risk Treatment).

This review evaluates the report across eight dimensions, highlighting its strengths and the areas requiring particular attention.

### 2. Assessment by Dimension

| Dimension | Assessment |
|---|---|
| Structure and organization | Strong |
| Scenario coverage | Good, subject to validation |
| Technical attack descriptions | Good, with some inconsistencies |
| Scoring methodology | Retained as established |
| Mathematical calculations | Generally correct |
| AI threat mapping | Needs substantial refinement if retained |
| Workshop traceability | Considered covered through connected reports |
| Presentation | Good foundation, requires polishing |

### 3. Detailed Assessment

#### 3.1 Structure and Organization

**Assessment: Strong**

The report follows a logical and coherent progression:

1. Methodology and assessment criteria.
2. Identification and description of operational scenarios.
3. Vulnerability score breakdown.
4. Summary and ranking of strategic scenarios.
5. Mapping to AI-specific threats.
6. Interpretation and conclusion.

This organization provides a clear progression from the assessment methodology to the results and their interpretation.

The overall structure is appropriate for a Workshop 4 deliverable and provides a suitable basis for presenting the operational risk analysis.

#### 3.2 Scenario Coverage

**Assessment: Good, subject to validation**

The report successfully develops 28 operational scenarios from the 14 strategic scenarios established previously.

The use of two operational scenarios per strategic scenario provides a useful level of detail and illustrates different execution channels and attack possibilities.

However, the number of scenarios alone does not guarantee complete coverage.

Some scenarios represent different execution channels of the same underlying attack rather than entirely independent attack paths.

The coverage is therefore considered good, although the distinction between alternative execution channels and genuinely different operational attack paths deserves attention.

#### 3.3 Technical Attack Descriptions

**Assessment: Good, with some inconsistencies**

The four-stage attack-path structure (Know, Enter, Find, Exploit) provides a clear and practical description of how an attacker could exploit a weakness.

Nevertheless, some descriptions combine different attack mechanisms within the same operational scenario.

For example, certain scenarios present exploitation of an unpatched service and the reuse of stolen credentials as alternative entry mechanisms. These approaches may involve different prerequisites and attack conditions.

Additionally, some vulnerability descriptions combine multiple weaknesses or missing security controls rather than identifying a single specific vulnerability.

Despite these observations, the attack descriptions provide a good technical foundation for understanding the operational scenarios.

#### 3.4 Scoring Methodology

**Assessment: Retained as established**

The report presents a scoring methodology based on five criteria:

- Attack vector.
- Attack complexity.
- Privileges required.
- User interaction.
- Impact on the targeted criterion.

The resulting vulnerability score is combined with the gravity level to establish the scenario's assessment value and corresponding treatment orientation.

The scoring methodology was established during the workshop and will be retained in its current form.

No methodological validation, recalibration or modification of the established scoring model is planned as part of this report revision.

#### 3.5 Mathematical Calculations

**Assessment: Generally correct**

The calculations presented in the operational scenario table, score breakdown and strategic scenario summary are generally consistent.

The report identifies:

- 28 operational scenarios.
- 14 scenarios classified as Avoid.
- 14 scenarios classified as Reduce.
- No scenarios classified as Accept or Neglect.

The ranking is also generally consistent with the calculated assessment values.

The numerical results provide a clear overview of the relative prioritization of the identified scenarios.

#### 3.6 AI Threat Mapping – ISO/IEC 27090

**Assessment: Needs substantial refinement if retained**

The report introduces an additional analysis linking the operational scenarios to AI-specific threats identified in ISO/IEC 27090.

This is a valuable extension because the system under analysis incorporates AI components, including models, training data, prediction services and anomaly-detection mechanisms.

However, some mappings require further clarification.

In particular, certain AI threats are presented as possible extensions of operational scenarios without being explicitly represented in their original attack paths.

There are also cases where the likelihood assigned to an AI-specific threat corresponds to the highest likelihood of the strategic scenario rather than the likelihood of the particular operational scenario associated with that threat.

**If this section is retained, the following modifications are recommended:**

1. **Improve operational traceability:** Link every identified AI threat to its actual operational scenario (SO), rather than relying exclusively on the strategic scenario (SS).

2. **Assign the corresponding likelihood:** Use the likelihood calculated for the relevant operational scenario. Avoid automatically transferring the highest likelihood of the strategic scenario to every associated AI threat.

3. **Distinguish direct mappings from hypothetical extensions:** Clearly separate AI threats explicitly represented in the operational attack paths from additional threats introduced as possible extensions.

4. **Validate AI threat classifications:** Ensure that the selected ISO/IEC 27090 threat categories accurately correspond to the described attack mechanisms.

**Optionality of this section**

The ISO/IEC 27090 mapping is an additional analytical component rather than an essential element of the operational scenario breakdown.

Consequently, the team may choose either to:

- Retain and refine the section according to the recommendations above.
- Remove the section entirely and keep Workshop 4 focused on operational scenario development and assessment.

Removing this section would not invalidate the core operational scenario analysis, provided that the operational scenarios themselves adequately describe the relevant risks.

The decision should depend on the intended scope and level of detail of the final deliverable.

#### 3.7 Workshop Traceability

**Assessment: Considered covered**

The Workshop 4 report is part of a consolidated risk assessment process and is intended to be read alongside the preceding workshop reports.

The relationship between strategic scenarios and operational scenarios is therefore established through the overall project documentation.

The consistency of scenario identifiers, descriptions and associated gravity levels across the workshop reports provides the necessary continuity.

No additional standalone traceability section is considered necessary, provided that the reports remain connected and the references between them are clear.

#### 3.8 Presentation and Documentation

**Assessment: Good foundation, requires polishing**

The report has a clear structure and contains substantial technical information.

Its presentation provides a good foundation for a formal project deliverable, although some documentation and formatting aspects could be improved.

The main observations concern table presentation, terminology consistency, references and overall document formatting.

### 4. Overall Conclusion

The Workshop 4 report represents a solid and sufficiently developed foundation for the operational analysis of the AI-SCMIS risk assessment.

Its principal strengths are the structured decomposition of strategic scenarios, the detailed operational attack paths, the vulnerability assessment and the consolidated scenario ranking.

The main areas requiring attention concern the consistency of certain technical attack descriptions, the presentation of vulnerabilities and the refinement of the document's overall presentation.

The ISO/IEC 27090 mapping remains an optional extension that may either be refined or removed depending on the team's decision.

The established scoring methodology and the relationship with previous workshop reports will remain unchanged.

Overall, the report provides a suitable basis for Workshop 5, where the identified risks will be addressed through the selection of security measures, treatment strategies, responsibilities and residual risk assessment.
