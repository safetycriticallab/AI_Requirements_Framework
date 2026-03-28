# AI Requirements Framework for Safety-Critical Systems

> Requirements and Verification Standards for Artificial Intelligence in Safety-Critical Applications

**Issuing Authority:** Safety Critical Labs | AI Certification Authority
**Version:** 1.0 | February 2025
**Status:** [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.19024421.svg)](https://doi.org/10.5281/zenodo.19024421)

---

## Overview

This framework establishes the AI-specific requirements and verifications against which Safety Critical Labs conducts certification assessments for systems incorporating artificial intelligence or machine learning capabilities in safety-critical applications.

Traditional software assurance assumes deterministic, logic-based systems with stable post-deployment behavior. AI and ML systems challenge this paradigm through probabilistic outputs, emergent behavior from training data, and potential performance degradation over time. This framework defines requirements and verification methods designed specifically for data-driven systems.

The framework is domain-agnostic and algorithm-agnostic. It applies across aerospace, aviation, automotive, medical, and other safety-critical domains without prescribing specific implementation approaches.

---

## AI System Classification

Systems are classified based on their impact on safety and operations, which determines applicable requirements and tailoring authority:

| Classification | Description | Applicable Requirements |
|---|---|---|
| **Safety-Critical AI** | AI outputs directly affect human safety or system survivability | AI-1 through AI-9 (no tailoring without Safety Review Board approval) |
| **Mission-Critical AI** | AI outputs affect operational success but not human safety | AI-1 through AI-9 (tailoring permitted with documented rationale) |
| **Mission Support AI** | AI supports operations but does not drive critical decisions | AI-1 through AI-5 minimum; AI-6 through AI-9 as tailored |

---

## Requirement Sets

The framework defines nine AI-specific requirement sets, each addressing a gap between traditional software verification and AI and ML system behavior:

| Req Set | Title | Gap Addressed |
|---|---|---|
| **AI-1** | Data Partitioning | Training data integrity and traceability |
| **AI-2** | Addressing AI Bias | Bias and fairness issues |
| **AI-3** | ML Test Coverage | No traditional test coverage equivalent for trained models |
| **AI-4** | Continuous Validation | Static after deployment assumptions; drift |
| **AI-5** | Hallucination Prevention | Unpredictable and fabricated outputs |
| **AI-6** | Out-of-Distribution Detection | Vulnerability to OOD inputs |
| **AI-7** | Adversarial Robustness | Vulnerability to adversarial attacks |
| **AI-8** | Explainability | Black-box decision making |
| **AI-9** | Human-AI Teaming | Operators cannot verify AI reasoning |

---

## Verification

Verification uses standard IEEE 1012 methods tailored for AI and ML systems:

| Method | AI Application |
|---|---|
| **Inspection** | Dataset documentation, provenance records, log schemas |
| **Analysis** | Bias risk assessment, coverage analysis, distribution characterization |
| **Demonstration** | Operator comprehension, human-AI interaction evaluation |
| **Test** | Drift detection, OOD detection, hallucination detection |

Each requirement includes co-located verification criteria and success criteria. A verification matrix in Section 3 provides full traceability.

---

## Document Structure

```
Section 1: Introduction
  1.1  Purpose
  1.2  Scope and Applicability
       1.2.1  Defining AI
       1.2.2  AI System Classification
       1.2.3  Relationship to Traditional Standards (Gap Analysis)
       1.2.4  Integration with Software Lifecycle
       1.2.5  Tailoring Guidance
  1.3  Normative References
  1.4  Verb Application and Lexicon
  1.5  Threshold Category Definitions

Section 2: Requirements (AI-1 through AI-9)

Section 3: Verification
  3.1  Verification Methods
  3.2  Verification Matrix Summary
  3.3  Deployment Format Validation

Section 4: Implementation Guidance
  4.1  Threshold Selection Guidance
  4.2  Continuous Learning Requirements
  4.3  Multi-Model System Considerations
  4.4  Neural Network Considerations
  4.5  AI-Specific Hazard Analysis Integration

Appendix A: Glossary (aligned with ISO/IEC 22989:2022, ISO/IEC 5338:2023)
Appendix B: AI Classification Checklist
Appendix C: Verification Evidence Templates
Appendix E: Source Traceability Matrix
```

---

## Normative References

| Document | Title |
|---|---|
| ISO/IEC 22989:2022 | AI Concepts and Terminology |
| ISO/IEC 5338:2023 | AI System Lifecycle Processes |
| NIST AI RMF 1.0 | AI Risk Management Framework |
| DO-178C | Software Considerations in Airborne Systems |
| ISO 26262 | Road Vehicles — Functional Safety |

---

## Getting Started

1. **Determine applicability** — Use the criteria in Section 1.2.1 and the checklist in Appendix B to identify whether your system incorporates AI and ML
2. **Classify your AI system** — Safety-Critical, Mission-Critical, or Mission Support (Section 1.2.2)
3. **Identify applicable requirements** — Based on classification (Table 1-3)
4. **Apply tailoring if needed** — Document rationale per Section 1.2.5
5. **Define thresholds** — Use Section 4.1 guidance to establish project-specific values
6. **Execute verification** — Use the verification matrix and evidence templates in Appendix C

---

## License

Creative Commons Attribution 4.0 International (CC BY 4.0)

---

## Contact

kevin.williams@safetycriticallabs.com
[safetycriticallabs.com](https://safetycriticallabs.com)
