# Awesome AI Governance [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> An opinionated list of resources for building, governing, and operating AI systems under the EU AI Act, ISO/IEC 42001, NIST AI RMF, the UK AI Cyber Code, and friends.

Curated by [@venkat-uk](https://github.com/venkat-uk). The bar for inclusion: would I send this link to a CTO who has 30 minutes and a Board paper due Friday? If yes, it is in. Otherwise, it is out.

Cross-posted with commentary at [themindfulcto.com](https://themindfulcto.com).

## Contents

- [Regulations and Standards](#regulations-and-standards)
- [Frameworks and Playbooks](#frameworks-and-playbooks)
- [Runtime Governance Tooling](#runtime-governance-tooling)
- [Evaluation and Red-Teaming](#evaluation-and-red-teaming)
- [Policy-as-Code](#policy-as-code)
- [Audit, Observability, and Traceability](#audit-observability-and-traceability)
- [AIBOM and Provenance](#aibom-and-provenance)
- [Incident Postmortems and Case Law](#incident-postmortems-and-case-law)
- [Books, Papers, and Long-form](#books-papers-and-long-form)
- [Communities](#communities)

## Regulations and Standards

The actual legal and standards corpus, prioritised by what UK and EU CTOs need to defend in front of a board.

- [EU AI Act](https://artificialintelligenceact.eu/the-act/) - The regulation itself, with a reading layer. Article 12 (logging) and Article 15 (accuracy, robustness, cybersecurity) are the runtime-enforceable ones.
- [ISO/IEC 42001:2023](https://www.iso.org/standard/42001) - The AI management-system standard auditors will ask about by name. Annex A controls map cleanly to engineering practice.
- [NIST AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework) - The US-side reference, well paired with the EU AI Act for multi-jurisdictional programmes.
- [UK AI Cyber Code of Practice](https://www.gov.uk/government/publications/ai-cyber-security-code-of-practice) - DSIT's voluntary code, becoming the de facto baseline for UK regulated estates.
- [OWASP Top 10 for LLM Applications](https://owasp.org/www-project-top-10-for-large-language-model-applications/) - Prompt injection, training data poisoning, model denial of service, and the rest.
- [OWASP Agentic Security Initiative](https://genai.owasp.org/initiatives/agentic-security-initiative/) - The agentic-specific extension, now under the OWASP GenAI Security Project. Emerging but already cited in policy.
- [Digital Operational Resilience Act (DORA)](https://www.eiopa.europa.eu/digital-operational-resilience-act-dora_en) - Financial-services regulation that interacts heavily with the EU AI Act for high-risk fintech systems.
- [NIS2 Directive](https://digital-strategy.ec.europa.eu/en/policies/nis2-directive) - Critical-infrastructure cybersecurity baseline that catches AI-enabled estates.

## Frameworks and Playbooks

Practitioner playbooks that compile the above into ways of working.

- [Microsoft Responsible AI Standard](https://www.microsoft.com/en-us/ai/principles-and-approach) - The most concretely operationalised responsible-AI framework from a hyperscaler, well suited for adoption by tier-1 enterprises.
- [People + AI Guidebook](https://pair.withgoogle.com/guidebook/) - Google PAIR's design-led guidance. Useful when product and design need a shared vocabulary with engineering.
- [IBM AI Ethics](https://www.ibm.com/impact/ai-ethics) - Board-level governance shape, helpful when standing up an AI ethics committee.
- [ICO Guidance on AI and Data Protection](https://ico.org.uk/for-organisations/uk-gdpr-guidance-and-resources/artificial-intelligence/guidance-on-ai-and-data-protection/) - The UK regulator's own AI auditing framework, essential for any UK programme.

## Runtime Governance Tooling

Where governance meets the production estate. Open-source first.

- [Guardrails AI](https://github.com/guardrails-ai/guardrails) - Input and output validators for LLM responses. Opinionated and well maintained.
- [NeMo Guardrails](https://github.com/NVIDIA/NeMo-Guardrails) - NVIDIA's programmatic guardrails for LLM applications. Production-grade.
- [Gram](https://github.com/speakeasy-api/gram) - Open-source control plane for MCPs, Skills, and Assistants. Enforces role-scoped access and records searchable events, giving teams a runtime governance point.

## Evaluation and Red-Teaming

The "did the AI do what we said it would do" tier.

- [Promptfoo](https://github.com/promptfoo/promptfoo) - Test-suite-shaped LLM eval framework. Sane defaults, good for CI/CD.
- [DeepEval](https://github.com/confident-ai/deepeval) - Pytest-style LLM evaluation that integrates cleanly with existing CI.
- [Ragas](https://github.com/explodinggradients/ragas) - The standard for RAG evaluation. Metrics include faithfulness, answer relevancy, and context precision and recall.
- [AgentDojo](https://github.com/ethz-spylab/agentdojo) - Academic benchmark for agentic prompt-injection robustness.
- [Langfuse](https://github.com/langfuse/langfuse) - Open-source LLM observability and evals, production-ready. Doubles as an audit log surface.

## Policy-as-Code

Run governance at request time.

- [Open Policy Agent](https://github.com/open-policy-agent/opa) - The de facto standard for policy-as-code. Rego language, mature ecosystem.
- [Cedar](https://github.com/cedar-policy/cedar) - AWS's authorisation policy language. Sometimes a cleaner fit than Rego for entitlement-shaped decisions.
- [Presidio](https://github.com/microsoft/presidio) - Microsoft's PII detection and anonymisation toolkit, with configurable recognisers for region-specific identifiers.
- [Rebuff](https://github.com/protectai/rebuff) - Prompt-injection detection layer that combines heuristics with LLM-as-judge.

## Audit, Observability, and Traceability

The evidence layer regulators will ask for. Langfuse, listed under Evaluation and Red-Teaming, belongs here too.

- [OpenTelemetry Generative AI semantic conventions](https://opentelemetry.io/docs/specs/semconv/gen-ai/) - The emerging standard for tracing LLM calls. Cross-vendor, cross-stack.
- [OpenLLMetry](https://github.com/traceloop/openllmetry) - OTel-based observability built specifically for LLM workloads.

## AIBOM and Provenance

The model-supply-chain layer.

- [SPDX AI Profile](https://spdx.dev/learn/areas-of-interest/ai/) - The SPDX standard's AI profile, designed for AIBOM use cases.
- [CycloneDX ML-BOM](https://cyclonedx.org/capabilities/mlbom/) - Alternative AIBOM specification under the OWASP CycloneDX umbrella.
- [Hugging Face Model Cards](https://huggingface.co/docs/hub/en/model-cards) - Practical model documentation pattern. The closest thing to a community standard.

## Incident Postmortems and Case Law

Real-world incidents and rulings. The tuition nobody wants to pay twice.

- [Moffatt v. Air Canada, 2024 BCCRT 149](https://www.canlii.org/en/bc/bccrt/doc/2024/2024bccrt149/2024bccrt149.html) - The BC Civil Resolution Tribunal ruling that established that your chatbot's claims bind you. Required reading.
- [Italian DPA measure on ChatGPT, 2023](https://www.garanteprivacy.it/web/guest/home/docweb/-/docweb-display/docweb/9870832) - The first major EU regulator move on a public LLM. Sets the GDPR-versus-LLM template.
- [ICO enforcement actions](https://ico.org.uk/action-weve-taken/enforcement/) - The UK regulator's running record of AI and automated-decisioning actions.

## Books, Papers, and Long-form

The slow-thinking tier.

- [Human Compatible](https://en.wikipedia.org/wiki/Human_Compatible) - Stuart Russell, 2019. The AI alignment book that an engineering leader can actually read and cite.
- [Weapons of Math Destruction](https://en.wikipedia.org/wiki/Weapons_of_Math_Destruction) - Cathy O'Neil, 2016. The canonical text on algorithmic harm, still the easiest way to explain risk to a non-technical board.
- [The Alignment Problem](https://en.wikipedia.org/wiki/The_Alignment_Problem) - Brian Christian, 2020. A sober, well-reported tour of alignment as it stands.

## Communities

The conversations that move faster than the standards.

- [MLOps Community](https://mlops.community/) - Slack, podcast, and conferences. The largest practitioner community for AI in production.
- [LF AI & Data](https://lfaidata.foundation/) - The Linux Foundation's umbrella for AI and data open-source governance.
- [AI Alliance](https://thealliance.ai/) - Open AI governance and standards work. IBM and Meta led, but multi-stakeholder.
- [OpenSSF](https://openssf.org/) - Open-source supply chain security. Relevant as the AI supply chain joins the software supply chain in practice.

## Contributing

Contributions are welcome. Read the [contribution guidelines](contributing.md) first. The standard for inclusion is "would I send this to a CTO under pressure".
