# Workshop 4 – Operational Scenarios
## Report Review and Recommendations

### 1. General Assessment

The Workshop 4 report (*Operational Scenarios*) provides a solid foundation for the operational analysis of the AI-Enabled Supply Chain Management Information System (AI-SCMIS).

The document demonstrates a structured approach to decomposing strategic scenarios into operational attack paths, identifying exploited vulnerabilities, describing attack sequences, and assessing their associated risk levels.

Overall, the report is well organized and contains the necessary elements to support the transition towards Workshop 5 (Risk Treatment).

The review identifies several areas that could benefit from clarification, refinement, and presentation improvements. These recommendations are intended to improve the report's quality without unnecessarily modifying its established methodology or overall structure.

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

### 3. Detailed Observations and Recommendations

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

**Recommendations:**

- Add an executive summary presenting the purpose, scope, principal findings, and overall results of Workshop 4.
- Add a brief introduction explaining the objectives of the workshop and its relationship with the preceding analysis.
- Improve the transition between the operational scenario analysis and the AI-specific threat mapping, if the latter section is retained.
- Preserve the existing overall section structure.

#### 3.2 Scenario Coverage

**Assessment: Good, subject to validation**

The report successfully develops 28 operational scenarios from the 14 strategic scenarios established previously.

The use of two operational scenarios per strategic scenario provides a useful level of detail and helps illustrate different execution channels and attack possibilities.

However, the number of scenarios alone does not guarantee complete coverage.

Some scenarios represent different execution channels of the same underlying attack, rather than entirely independent attack paths.

**Recommendations:**

- Ensure that each operational scenario represents a sufficiently coherent attack sequence.
- Review scenarios where different entry mechanisms are combined within the same attack path.
- Distinguish between alternative execution channels and genuinely different operational attack paths.
- Ensure that the vulnerabilities described are relevant to the specific attack being developed.
- Maintain the relationship between each operational scenario and its corresponding strategic scenario.

#### 3.3 Technical Attack Descriptions

**Assessment: Good, with some inconsistencies**

The four-stage attack-path structure (Know, Enter, Find, Exploit) provides a clear and practical description of how an attacker could exploit a weakness.

Nevertheless, some descriptions combine different attack mechanisms within the same operational scenario.

For example, certain scenarios present exploitation of an unpatched service and the reuse of stolen credentials as alternative entry mechanisms.

These approaches may involve different prerequisites and attack conditions.

Additionally, some vulnerability descriptions combine multiple weaknesses or missing security controls.

**Recommendations:**

- Review attack paths that combine materially different entry mechanisms.
- Ensure consistency between the described attack path and its associated vulnerability.
- Distinguish vulnerabilities and weaknesses from the actions performed by the attacker.
- Make sure each scenario describes a coherent progression from initial knowledge to exploitation.
- Where multiple weaknesses are identified, make their respective contributions to the attack explicit.

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

**Recommendations:**

- Preserve the established scoring criteria, weighting and calculation method.
- Retain the current decision thresholds.
- Ensure that the score breakdown remains consistent with the values presented in the operational scenario table.
- Resolve any remaining documentation placeholders concerning the scoring assumptions.

No methodological validation or recalibration of the scoring model is planned as part of this report revision.

#### 3.5 Mathematical Calculations

**Assessment: Generally correct**

The calculations presented in the operational scenario table, score breakdown and strategic scenario summary are generally consistent.

The report identifies:

- 28 operational scenarios.
- 14 scenarios classified as Avoid.
- 14 scenarios classified as Reduce.
- No scenarios classified as Accept or Neglect.

The ranking is also consistent with the calculated assessment values.

**Recommendations:**

- Preserve the existing calculations.
- Ensure that values remain consistent across all tables and summaries.
- Verify that the final conclusion accurately reflects the results presented in the report.

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

**Optionality of this section:**

The ISO/IEC 27090 mapping is an additional analytical component rather than an essential element of the operational scenario breakdown.

Consequently, the team may choose either to:

- Retain and refine the section according to the recommendations above.
- Remove the section entirely and keep Workshop 4 focused on operational scenario development and assessment.

Removing this section would not invalidate the core operational scenario analysis, provided that the scenarios themselves adequately describe the relevant AI-related risks.

The decision should depend on the intended scope and level of detail of the final deliverable.

#### 3.7 Workshop Traceability

**Assessment: Considered covered**

The Workshop 4 report is part of a consolidated risk assessment process and is intended to be read alongside the preceding workshop reports.

The relationship between strategic scenarios and operational scenarios is therefore established through the overall project documentation.

**Recommendations:**

- Preserve consistent scenario identifiers across the different workshop reports.
- Maintain the same strategic scenario descriptions and gravity levels established in Workshop 3.
- Ensure that the operational scenarios remain identifiable as refinements of the previously established strategic scenarios.

No additional standalone traceability section is considered necessary, provided that the reports remain connected and the references between them are clear.

#### 3.8 Presentation and Documentation

**Assessment: Good foundation, requires polishing**

The report has a clear structure and contains substantial technical information. However, several presentation improvements would make it more suitable as a formal project deliverable.

**Recommendations:**

- Add numbered captions to all tables.
- Introduce a consistent terminology and abbreviations section.
- Standardize technical terminology and remove any remaining untranslated expressions.
- Add a references section for the standards and methodological documents actually used.
- Improve the readability of wide tables and ensure consistent formatting.
- Remove unresolved drafting notes and placeholders before final submission.

### 4. Prioritized Revision Plan

| Priority | Revision | Expected result |
|---|---|---|
| 1 | Review operational attack descriptions | More coherent and consistent scenarios |
| 2 | Review scenario vulnerabilities and their descriptions | Clearer relationship between weaknesses and attack paths |
| 3 | Decide whether to retain the ISO/IEC 27090 mapping | A clear and justified scope for the report |
| 4 | If retained, refine the AI threat mapping | Improved technical accuracy and traceability |
| 5 | Finalize presentation and documentation | Professional and consistent deliverable |

The established scoring methodology and its calculations are to be preserved during these revisions.

### 5. Conclusion

The Workshop 4 report represents a solid and sufficiently developed foundation for the operational analysis of the AI-SCMIS risk assessment.

Its principal strengths are the structured decomposition of strategic scenarios, the detailed operational attack paths, the vulnerability assessment and the consolidated scenario ranking.

The proposed revisions focus primarily on improving the coherence of attack descriptions, clarifying the relationship between vulnerabilities and exploitation mechanisms, and refining the presentation of the final document.

The ISO/IEC 27090 mapping should be treated as an optional extension, with the possibility of retaining it after refinement or removing it to maintain a more focused operational analysis.

The established scoring methodology and the relationship with previous workshop reports will remain unchanged.

Following these adjustments, the report should provide a suitable and coherent basis for Workshop 5, where the identified risks will be addressed through the selection of security measures, treatment strategies, responsibilities and residual risk assessment.
