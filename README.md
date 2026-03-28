# AI Requirements Framework for Safety-Critical Systems

> Requirements and Verification Standards for Artificial Intelligence in Human-Rated Applications

**Author:** Kevin Williams  
**Version:** 1.0 | February 2025  
**Status:** [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.19024421.svg)](https://doi.org/10.5281/zenodo.19024421)

---

## Overview

This framework establishes AI-specific requirements and corresponding verification methods to supplement traditional software engineering standards (e.g., NASA NPR 7150.2D, DO-178C, ISO 26262) for systems incorporating artificial intelligence or machine learning in safety-critical applications.

Traditional software assurance assumes deterministic, logic-based systems with stable post-deployment behavior. AI/ML systems challenge this paradigm through probabilistic outputs, emergent behavior from training data, and potential performance degradation over time. This framework bridges that gap.

### Key Principles

- **Supplements, does not replace** existing software and model assurance requirements
- **Addresses AI/ML-specific failure modes** not covered by traditional software verification
- **Domain-agnostic** — applicable to aerospace, automotive, medical, industrial, and other safety-critical domains
- **Algorithm-agnostic** — requirements do not prescribe specific implementation approaches

---

## AI System Classification

Systems are classified based on their impact on safety and operations, which determines the applicable requirements and tailoring authority:

| Classification | Description | Applicable Requirements |
|---|---|---|
| **Safety-Critical AI** | AI outputs directly affect human safety or system survivability | All AI-1 through AI-9 (no tailoring without PSRB approval) |
| **Mission-Critical AI** | AI outputs affect operational success but not human safety | AI-1 through AI-9 (tailoring permitted with CE approval) |
| **Mission Support AI** | AI supports operations but does not drive critical decisions | AI-1 through AI-5 minimum; AI-6–AI-9 as tailored |

---

## Requirement Sets

The framework defines nine AI-specific requirement sets, each addressing a gap between traditional software verification and AI/ML system behavior:

| Req Set | Title | Gap Addressed |
|---|---|---|
| **AI-1** | Data Partitioning | Training data integrity and traceability |
| **AI-2** | Addressing AI Bias | Bias and fairness issues |
| **AI-3** | ML Test Coverage | No traditional test coverage equivalent for trained models |
| **AI-4** | Continuous Validation | Static-after-deployment assumptions; drift |
| **AI-5** | Hallucination Prevention | Unpredictable / fabricated outputs |
| **AI-6** | Out-of-Distribution Detection | Vulnerability to OOD inputs |
| **AI-7** | Adversarial Robustness | Vulnerability to adversarial attacks |
| **AI-8** | Explainability | Black-box decision making |
| **AI-9** | Human-AI Teaming | Operators cannot verify AI reasoning |

### AI-1: Data Partitioning

Ensures integrity of training, validation, and test datasets throughout the model lifecycle. Covers dataset separation, partition use restriction, data provenance, and ground truth labeling quality.

### AI-2: Addressing AI Bias

Implements bias detection, prevention, and mitigation across all operational scenarios and user populations. Includes 13 sub-requirements covering baseline performance, training data validation, continuous monitoring, impact assessment, threshold alerting/response, event logging, safety-critical bias prohibition/escalation, and edge case validation.

### AI-3: ML Test Coverage

Demonstrates adequate test coverage using methods appropriate to data-driven systems where traditional code coverage metrics do not apply. Covers metric definition, threshold achievement, operational input distribution testing, and boundary/edge case testing.

### AI-4: Continuous Validation

Ensures model performance remains within acceptable bounds throughout operational deployment. Addresses data drift monitoring, performance threshold maintenance, model maintenance criteria, output validity boundaries, and periodic model validation.

### AI-5: Hallucination Prevention

Detects, prevents, and mitigates AI outputs that are fabricated, unsupported by input data, or inconsistent with operational reality. Covers criteria definition, detection mechanisms, response procedures, logging, and independent output validation for safety-critical functions.

### AI-6: Out-of-Distribution Detection

Detects and handles inputs that fall outside the training data distribution. Includes training distribution characterization, runtime OOD detection, OOD response procedures, and event logging.

### AI-7: Adversarial Robustness

Protects against adversarial attacks including data poisoning, adversarial input manipulation, model inversion/extraction, and supply chain threats. Also covers model integrity verification and adversarial event logging.

### AI-8: Explainability

Provides explanations of AI decisions sufficient for operators to verify reasoning and establish appropriate trust. Addresses requirements definition, decision explanation generation, confidence indication, and reasoning inspection capability.

### AI-9: Human-AI Teaming

Supports effective human-AI collaboration with operator situational awareness, trust calibration, and final decision authority over safety-critical actions. Covers human decision authority, situational awareness, trust calibration, graceful degradation, and interaction logging.

---

## Verification

Verification uses standard IEEE 1012 methods tailored for AI/ML:

| Method | AI Application |
|---|---|
| **Inspection** | Dataset documentation, provenance records, log schemas |
| **Analysis** | Bias risk assessment, coverage analysis, distribution characterization |
| **Demonstration** | Operator comprehension, human-AI interaction evaluation |
| **Test** | Drift detection, OOD detection, hallucination detection |

Each requirement includes co-located verification criteria and success criteria. A verification matrix in Section 3 provides full traceability.

### Deployment Format Validation

Models transformed for edge deployment (quantization, pruning, knowledge distillation, framework conversion) must be revalidated against the original trained model with documented performance comparisons.

---

## Implementation Guidance (Section 4)

The framework includes informative (non-normative) guidance on:

- **Threshold Selection** — Example ranges for bias metrics, drift detection, confidence calibration, and more, scaled by system classification
- **Continuous Learning** — Classification-based controls for systems that learn during operation, including catastrophic forgetting mitigation
- **Multi-Model Systems** — Cascading failure considerations, ensemble/voting systems, and confidence aggregation
- **Neural Network Considerations** — Explainability approaches, training/validation pitfalls, deployment transformation sensitivity, and architecture-specific failure modes
- **AI-Specific Hazard Analysis** — Integrating AI failure modes (data-related, model-related, operational, adversarial, human factors) into FMEA/FTA/HAZOP

---

## Document Structure

```
Section 1: Introduction
  ├── 1.1  Purpose
  ├── 1.2  Scope and Applicability
  │        ├── Defining AI
  │        ├── AI System Classification
  │        ├── Relationship to Traditional Standards (Gap Analysis)
  │        ├── Integration with Software Lifecycle
  │        └── Tailoring Guidance
  ├── 1.3  Normative References
  └── 1.4  Verb Application and Lexicon

Section 2: Requirements (AI-1 through AI-9 + AI-10 Threshold Categories)

Section 3: Verification
  ├── 3.1  Verification Methods
  ├── 3.2  Verification Matrix Summary
  └── 3.3  Deployment Format Validation

Section 4: Implementation Guidance

Appendix A: Glossary (aligned with ISO/IEC 22989, ISO/IEC 5338)
Appendix B: AI Classification Checklist
Appendix C: Verification Evidence Templates
Appendix D: Standards Crosswalk (ISO 5338 ↔ NPR 7150.2D)
Appendix E: Source Traceability Matrix
```

---

## Normative References

| Document | Title |
|---|---|
| NPR 7150.2D | NASA Software Engineering Requirements |
| NASA-STD-8739.8 | Software Assurance and Safety Standard |
| ISO/IEC 22989:2022 | AI Concepts and Terminology |
| ISO/IEC 5338:2023 | AI System Lifecycle Processes |
| NIST AI RMF 1.0 | AI Risk Management Framework |
| DO-178C | Software Considerations in Airborne Systems |
| ISO 26262 | Road Vehicles — Functional Safety |

---

## Getting Started

1. **Determine applicability** — Use the criteria in Section 1.2.1 and the checklist in Appendix B to identify whether your system incorporates AI/ML
2. **Classify your AI system** — Safety-Critical, Mission-Critical, or Mission Support (Section 1.2.2)
3. **Identify applicable requirements** — Based on classification (Table 1-3)
4. **Apply tailoring if needed** — Document rationale per Section 1.2.5
5. **Integrate with your software lifecycle** — AI activities map to existing lifecycle phases (Table 1-6)
6. **Define thresholds** — Use Section 4.1 guidance to establish project-specific values
7. **Execute verification** — Use the verification matrix and evidence templates (Appendix C)

---

## License

DRAFT — Not yet released for public distribution.

---

## Contact

**Kevin Williams**  
kevin.williams@safetycriticallabs.com
