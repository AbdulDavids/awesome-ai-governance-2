# Awesome AI Governance [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> A curated, opinionated list of resources for building, governing, and operating AI systems under EU AI Act, ISO/IEC 42001, NIST AI RMF, UK AI Cyber Code, and friends.

Curated by [@venkat-uk](https://github.com/venkat-uk). The bar for inclusion: would I send this link to a CTO who has 30 minutes and a Board paper due Friday? If yes, it's in. Otherwise, it's out.

Cross-posted with commentary at [themindfulcto.com](https://themindfulcto.com).

---

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

---

## Regulations and Standards

The actual legal and standards corpus, prioritised by what UK and EU CTOs need to defend in front of a board.

- **[EU AI Act](https://artificialintelligenceact.eu/the-act/)** — the regulation itself, with reading layer. Article 12 (logging) and Article 15 (accuracy, robustness, cybersecurity) are the runtime-enforceable ones.
- **[ISO/IEC 42001:2023 — AI Management Systems](https://www.iso.org/standard/42001)** — the management-system standard auditors will ask about by name. Annex A controls map cleanly to engineering practice.
- **[NIST AI Risk Management Framework (AI RMF 1.0)](https://www.nist.gov/itl/ai-risk-management-framework)** — the US-side reference, well-paired with the EU AI Act for multi-jurisdictional programmes.
- **[UK AI Cyber Code of Practice](https://www.gov.uk/government/publications/ai-cyber-security-code-of-practice)** — DSIT's voluntary code, becoming the de facto baseline for UK regulated estates.
- **[OWASP Top 10 for LLM Applications](https://owasp.org/www-project-top-10-for-large-language-model-applications/)** — Prompt injection, training data poisoning, model denial of service, and the rest.
- **[OWASP Agentic Security Initiative](https://genai.owasp.org/initiatives/agentic-security-initiative/)** — the agentic-specific extension; emerging but already cited in policy.
- **[DORA — Digital Operational Resilience Act](https://www.eiopa.europa.eu/digital-operational-resilience-act-dora_en)** — financial-services horizontal regulation that interacts heavily with AI Act for high-risk fintech systems.
- **[NIS2 Directive](https://digital-strategy.ec.europa.eu/en/policies/nis2-directive)** — critical-infrastructure cybersecurity baseline that catches AI-enabled estates.

## Frameworks and Playbooks

Practitioner playbooks that compile the above into ways of working.

- **[Microsoft Responsible AI Standard v2](https://www.microsoft.com/en-us/ai/principles-and-approach)** — the most concretely operationalised RAI framework from a hyperscaler, well-suited for adoption by tier-1 enterprises.
- **[Google PAIR (People + AI Guidebook)](https://pair.withgoogle.com/guidebook/)** — design-led; useful when product and design need a shared vocabulary with engineering.
- **[IBM AI Ethics Board guidance](https://www.ibm.com/impact/ai-ethics)** — board-level governance shape, helpful when standing up an AI ethics committee.
- **[ICO AI Auditing Framework (UK)](https://ico.org.uk/for-organisations/uk-gdpr-guidance-and-resources/artificial-intelligence/guidance-on-ai-and-data-protection/)** — the UK regulator's own AI auditing framework, essential for any UK programme.

## Runtime Governance Tooling

Where governance meets the production estate. Open-source first.

- **[Guardrails AI](https://github.com/guardrails-ai/guardrails)** — input/output validators for LLM responses; opinionated and well-maintained.
- **[NeMo Guardrails (NVIDIA)](https://github.com/NVIDIA/NeMo-Guardrails)** — programmatic guardrails for LLM applications; production-grade.

## Evaluation and Red-Teaming

The "did the AI do what we said it would do" tier.

- **[Promptfoo](https://github.com/promptfoo/promptfoo)** — test-suite-shaped LLM eval framework; sane defaults, good for CI/CD.
- **[DeepEval](https://github.com/confident-ai/deepeval)** — pytest-style LLM evaluation; integrates cleanly with existing CI.
- **[Ragas](https://github.com/explodinggradients/ragas)** — the standard for RAG evaluation; metrics include faithfulness, answer relevancy, context precision/recall.
- **[AgentDojo](https://github.com/ethz-spylab/agentdojo)** — academic benchmark for agentic prompt-injection robustness.
- **[Langfuse](https://github.com/langfuse/langfuse)** — open-source LLM observability and evals; production-ready.

## Policy-as-Code

Run governance at request time.

- **[Open Policy Agent (OPA)](https://github.com/open-policy-agent/opa)** — the de facto standard for policy-as-code; Rego language, mature ecosystem.
- **[Cedar](https://github.com/cedar-policy/cedar)** — AWS's authorisation policy language; sometimes a cleaner fit than Rego for entitlement-shaped decisions.
- **[Microsoft Presidio](https://github.com/microsoft/presidio)** — PII detection and anonymisation; configurable recognisers for region-specific identifiers.
- **[Rebuff](https://github.com/protectai/rebuff)** — prompt-injection detection layer; combines heuristics with LLM-as-judge.

## Audit, Observability, and Traceability

The evidence layer regulators will ask for.

- **[OpenTelemetry Generative AI semantic conventions](https://opentelemetry.io/docs/specs/semconv/gen-ai/)** — the emerging standard for tracing LLM calls; cross-vendor, cross-stack.
- **[OpenLLMetry](https://github.com/traceloop/openllmetry)** — OTel-based observability built specifically for LLM workloads.

## AIBOM and Provenance

The model-supply-chain layer.

- **[SPDX 3.0 AI Profile](https://spdx.dev/learn/areas-of-interest/ai/)** — the SPDX standard's AI profile, designed for AIBOM use cases.
- **[CycloneDX ML-BOM](https://cyclonedx.org/capabilities/mlbom/)** — alternative AIBOM specification under the OWASP CycloneDX umbrella.
- **[Hugging Face Model Cards](https://huggingface.co/docs/hub/en/model-cards)** — practical model documentation pattern; the closest thing to a community standard.

## Incident Postmortems and Case Law

Real-world incidents and rulings. The teacher's salary nobody pays.

- **[Moffatt v. Air Canada, 2024 BCCRT 149](https://www.canlii.org/en/bc/bccrt/doc/2024/2024bccrt149/2024bccrt149.html)** — the case that established "your chatbot's claims bind you." Required reading.
- **[Italian DPA ban on ChatGPT, 2023](https://www.garanteprivacy.it/web/guest/home/docweb/-/docweb-display/docweb/9870832)** — the first major EU regulator move on a public LLM; sets the GDPR-vs-LLM template.
- **[ICO enforcement actions on AI/automated decisioning (UK)](https://ico.org.uk/action-weve-taken/enforcement/)** — UK regulator's running record of AI-related actions.

## Books, Papers, and Long-form

The slow-thinking tier.

- **Stuart Russell, _Human Compatible_ (2019)** — the AI alignment book that an engineering leader can actually read and cite.
- **Cathy O'Neil, _Weapons of Math Destruction_ (2016)** — the canonical text on algorithmic harm, still the easiest way to explain risk to a non-technical board.
- **Brian Christian, _The Alignment Problem_ (2020)** — a sober, well-reported tour of alignment as it stands.

## Communities

The conversations that move faster than the standards.

- **[MLOps Community](https://mlops.community/)** — Slack, podcast, conferences; the largest practitioner community for AI in production.
- **[LF AI & Data](https://lfaidata.foundation/)** — the Linux Foundation's umbrella for AI/data OSS governance.
- **[AI Alliance](https://thealliance.ai/)** — open AI governance and standards work, IBM/Meta-led but multi-stakeholder.
- **[OpenSSF](https://openssf.org/)** — open-source supply chain security; relevant as AI supply chain joins software supply chain in practice.

---

## Contributing

PRs welcome. The standard for inclusion is "would I send this to a CTO under pressure". One line of why-it's-here per entry. No tool listings without justification. No marketing pages. Open an issue first if in doubt.

## License

[![CC BY-SA 4.0](https://licensebuttons.net/l/by-sa/4.0/88x31.png)](https://creativecommons.org/licenses/by-sa/4.0/)

This work is licensed under a [Creative Commons Attribution-ShareAlike 4.0 International License](https://creativecommons.org/licenses/by-sa/4.0/).
