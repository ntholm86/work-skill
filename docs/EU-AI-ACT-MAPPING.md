# Work, PEA, and the EU AI Act

**Status:** evidence map, not legal advice or a compliance declaration.

This document maps the capabilities of [`work/SKILL.md`](../work/SKILL.md), the Principles of Earned Autonomy (PEA), and [`llm-harness-proxy`](https://github.com/ntholm86/llm-harness-proxy) to selected provisions of Regulation (EU) 2024/1689 (the EU AI Act).

It is deliberately narrower than an AI Act compliance assessment. Work is a reasoning and audit workflow. The harness is an optional API-traffic capture proxy. Neither classifies an AI system, supplies conformity assessment, or makes a provider or deployer compliant by itself.

## Legal timing

[Article 113](https://artificialintelligenceact.eu/article/113/) makes the Regulation generally applicable from **2 August 2026**. It separately makes Chapter I, including [Article 4](https://artificialintelligenceact.eu/article/4/), applicable from **2 February 2025**; some provisions, including Chapter V, applied from **2 August 2025**; and Article 6(1) product-safety obligations apply from 2 August 2027.

The date does not decide whether a particular organisation has an obligation. That depends on its role, the system's intended purpose, whether it is high-risk, whether it is a GPAI model or system, and other applicable Union and national law.

## What each component actually does

| Component | Actual capability | Evidence boundary |
| --- | --- | --- |
| PEA | A governance stance: Operator's Intent, Observable Autonomy, and Convergence Is Silence. | Principles are not legal controls and do not demonstrate compliance. |
| Work | Requires a confirmed operator Destination before decision-bearing work; risk-sized examination; pre-action predictions; append-only semantic Trail; explicit human decision points; and triggered re-orientation. | The Trail is agent-authored. It records declared reasoning and outcomes, not a verified copy of internal model computation. |
| Harness | Captures supported LLM API requests and responses in a hash-chained JSONL ledger. In buffered mode, a response is withheld when the ledger write or `fsync` fails. | It sees only traffic routed through it. Provider reasoning is optional and provider-specific. Streaming forwards content before final persistence, so strict fail-closed release does not hold there. |

The combined design is strongest where a deployment needs both a readable account of why a decision was made and independent evidence of what crossed the model API boundary. The two records must remain distinct: Work's Trail explains a decision; the harness ledger supplies captured traffic evidence. A disagreement is evidence to investigate, not something to reconcile silently.

## Provision map

The labels below are intentionally conservative:

- **Workflow support:** the combined design can supply a useful operating control or evidence input when deployed and followed.
- **Evidence support:** it can contribute records, but does not meet the legal requirement on its own.
- **No coverage:** the requirement needs controls outside Work and the harness.

| EU AI Act reference | What the provision requires | Work + harness contribution | Honest status and missing control |
| --- | --- | --- | --- |
| [Art. 4](https://artificialintelligenceact.eu/article/4/) | Providers and deployers must take measures, to their best extent, for sufficient AI literacy of staff and people operating AI on their behalf, considering skill and context. | Work defines a repeatable operating discipline, explains when an operator must decide, and makes limitations and evidence boundaries explicit. | **Evidence support only.** A skill file is not a literacy programme, competence assessment, training record, or proof that the relevant staff understand a particular system. |
| [Art. 9(1)-(8)](https://artificialintelligenceact.eu/article/9/) | High-risk providers need a documented, continuous lifecycle risk-management system: identify, evaluate, mitigate, test, and review risks, including post-market evidence. | Work requires a risk-sized target map, a falsifiable model, route comparison, structural challenge, pre-action prediction, and recorded reversal. Harness sessions can preserve evidence relevant to an identified risk or surprise. | **Workflow support only.** It is not a lifecycle risk-management system, hazard analysis, residual-risk judgment, defined metric/threshold regime, or required testing programme. |
| [Art. 11 and Annex IV](https://artificialintelligenceact.eu/article/11/) | High-risk providers must prepare and maintain technical documentation before placing a system on the market or putting it into service, sufficient for authorities to assess compliance. | Destination, Orientation, Trail, versioned source, test results, and relevant harness sessions can be organised as source material for technical documentation. | **Evidence support only.** Work does not generate or validate Annex IV documentation, system description, data information, performance evidence, conformity material, or authority-ready technical documentation. |
| [Art. 12(1)-(2)](https://artificialintelligenceact.eu/article/12/) | High-risk systems must technically allow automatic event logging appropriate to traceability, risk identification, monitoring, and post-market monitoring. | When every relevant supported LLM call is routed through the harness, its session ledger automatically records timestamps, model identity, input digest, provider-exposed reasoning where available, tool calls, outputs, and hash-chain links. | **Partial evidence support.** This is API-boundary logging, not proof of complete system logging. It does not capture bypassed calls, local model activity, external tools, user-interface events, or every event material to a high-risk system. |
| [Art. 13(1)-(3)](https://artificialintelligenceact.eu/article/13/) | High-risk systems must be transparent enough for deployers to interpret outputs and use them appropriately; instructions must state intended purpose, capabilities, limitations, risks, oversight, and logging information. | Work requires target-specific limits, uncertainty, source boundaries, human legibility, and a documented explanation of the route chosen. The harness specification documents its own capture and streaming limits. | **Evidence support only.** Neither component creates complete instructions for use for a deployed AI system, validates expected performance, or supplies all provider information required by Article 13. |
| [Art. 14(1)-(4)](https://artificialintelligenceact.eu/article/14/) | High-risk systems must enable effective, risk-proportionate human oversight, including understanding limits, avoiding automation bias, interpreting output, overriding it, and intervening or stopping the system. | Work keeps Destination authority with the operator, treats hunches as non-operative until confirmed, requires human-readable reasoning, and requires an operator decision before redesign. The harness makes captured traffic reviewable independently of the agent's own Trail. | **Workflow support only.** Work cannot assign competent overseers, ensure their training or authority, prevent automation bias, or provide a technical stop/override mechanism for an arbitrary deployed system. The harness gates response delivery, not every downstream action. |
| [Art. 17(1)](https://artificialintelligenceact.eu/article/17/) | High-risk providers need a documented quality-management system covering compliance strategy, design, testing, risk, post-market monitoring, reporting, records, resources, and accountability. | Work supplies a small auditable decision procedure and durable record; the harness supplies an independent evidence tier for supported interactions. | **No compliance coverage.** These tools are not a quality-management system, accountability assignment, resource-management control, or substitute for organisational policies and procedures. |
| [Art. 18](https://artificialintelligenceact.eu/article/18/) | High-risk providers must keep specified technical, quality, notified-body, and conformity documents available to authorities for ten years. | Work and harness records can be retained as supporting evidence. | **Evidence support only.** Neither imposes a ten-year retention schedule, records every required document, preserves legal availability, or manages authority access. |
| [Art. 19](https://artificialintelligenceact.eu/article/19/) and [Art. 26(6)](https://artificialintelligenceact.eu/article/26/) | Providers and deployers of high-risk systems must retain controlled automatic logs for an appropriate period, at least six months unless other law applies. | The harness creates automatic, hash-chained session logs for routed traffic; Work can point a material Trail entry to relevant evidence instead of copying raw traffic into prose. | **Partial evidence support.** Retention, access control, backup, deletion, data-protection assessment, and the six-month minimum must be configured and evidenced by the organisation. The current harness does not turn its logs into a universal system-of-record. |
| [Art. 26(1)-(5), (11)-(12)](https://artificialintelligenceact.eu/article/26/) | High-risk deployers must follow instructions, assign trained oversight, use relevant controlled inputs, monitor operation, suspend/report risks and incidents, and inform affected persons in relevant Annex III decisions. | Work can document a deployer's decision route, input relevance questions, a detected contradiction or reversal, and an operator's intervention. Harness records may help investigate an observed interaction. | **Workflow support only.** The tools do not monitor a deployed system continuously, classify incidents, suspend a system, report to a provider or authority, inform affected people, or satisfy role-specific deployer duties. |
| [Art. 50](https://artificialintelligenceact.eu/article/50/) | Certain providers and deployers must inform people they are interacting with AI; mark synthetic outputs in machine-readable form where required; and disclose specified deepfake or public-interest text uses. | Work encourages honest descriptions of evidence and limits. The harness can record whether a supported model interaction occurred. | **No coverage.** Neither tool automatically displays an AI notice, creates machine-readable provenance labels, detects deepfakes, identifies public-interest publication, or makes the required disclosure. Article 50 applies from 2 August 2026. |
| [Art. 72](https://artificialintelligenceact.eu/article/72/) | High-risk providers need a documented, proportionate post-market monitoring system that actively and systematically collects, documents, and analyses relevant performance data throughout the system's lifetime. | Work's Trail and triggered Orient can make a change, failed prediction, reversal, or recurring finding visible. The harness can retain relevant captured interactions for review. | **Evidence support only.** This is not active and systematic post-market monitoring, a monitoring plan, performance analytics, lifecycle data collection, or continuous-compliance assessment. |

## Hard boundaries

The combined design does **not** solve the following AI Act obligations or adjacent legal duties:

- Risk classification, prohibited-practice analysis, or an Annex III determination.
- Provider or deployer role allocation across a value chain.
- Data governance, representativeness, bias controls, privacy, DPIAs, security, robustness, accuracy, or cybersecurity testing.
- Fundamental-rights impact assessments under Article 27.
- Conformity assessment, harmonised standards, common specifications, EU declaration of conformity, CE marking, registration, or authority cooperation.
- GPAI-provider documentation, copyright-policy, or systemic-risk duties under Articles 53-55.
- Incident reporting, corrective action, worker notices, or public/user transparency notices.
- A guarantee that a model's visible reasoning is causally faithful to its internal computation.
- Capture of activity that does not traverse the harness, or tamper-proof evidence against every actor. The current protocol is hash-chained, but does not provide signatures, encryption, distributed consensus, or a complete endpoint-security model.

## Conditions for using the evidence responsibly

A deployment that wants to rely on this architecture as supporting evidence should, at minimum:

1. Determine its legal role and system classification before mapping any control to an AI Act obligation.
2. Keep Work's semantic Trail and the harness ledger separate, identify the relevant session in material Trail entries, and preserve disagreement between them.
3. Verify that the harness is actually on the relevant API path, identify whether the interaction was buffered or streamed, and state which provider fields were available.
4. Set organisation-owned retention, access, privacy, security, and incident procedures around the captured records.
5. Convert the resulting evidence into the provider/deployer documentation and controls required for the concrete system, with legal and technical review.

## Source and maintenance note

Legal text links point to the AI Act Explorer pages at [artificialintelligenceact.eu](https://artificialintelligenceact.eu/), which identifies its text as Regulation (EU) 2024/1689, Official Journal version of 13 June 2024. This document was reviewed on 28 July 2026. Check the official text, adopted implementing acts, guidance, and applicable national law before relying on it for a deployment decision.

Implementation claims are tied to the current local contracts:

- [`work/SKILL.md`](../work/SKILL.md)
- [`llm-harness-proxy README`](../../llm-harness-proxy/README.md)
- [`llm-harness-proxy protocol specification`](../../llm-harness-proxy/SPEC.md)
