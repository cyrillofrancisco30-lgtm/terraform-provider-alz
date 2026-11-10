

# XA-TRUST-DOD-CROSSWALK v2.0

## Technical Evidence Mapping \& Independent Validation Specification

**Document ID:** XA-TRUST-DOD-CROSSWALK-SPEC-002
**Version:** 2.0.0
**Status:** DRAFT — PROPOSED
**Baseline:** `4e5dec8403b15535943e21b66a52b243d0669d1a`
**Repository:** `cyrillofrancisco30-lgtm/terraform-provider-alz`
**Source document:** `docs/XA-TRUST-DOD-CROSSWALK.md`

---

## 1\. Purpose

This specification establishes a controlled methodology for mapping XA-TRUST architectural components and evidence capabilities to the seven pillars and 45 capabilities of the US Department of Defense Zero Trust framework.

The purpose is to establish traceability between:

1. Official DoD capability requirements.
2. XA-TRUST architectural components.
3. Implemented controls.
4. Execution evidence.
5. Reproducible test results.
6. Independent verification.
7. Claim-scoped conclusions.

This document does not establish DoD certification, accreditation, regulatory approval or official recognition.

## 2\. Normative principles

The following distinctions are mandatory:

- ARCHITECTURAL\_MAPPING != IMPLEMENTATION.
- IMPLEMENTATION != EXECUTION\_EVIDENCE.
- EXECUTION\_SUCCESS != SECURITY\_EFFECTIVENESS.
- HASH\_MATCH != SEMANTIC\_TRUTH.
- SIGNATURE\_VALID != AUTHORIZED\_SIGNER.
- LEDGER\_ANCHORED != SOURCE\_AUTHENTICITY.
- REPLAY\_SUCCESS != REGULATORY\_APPROVAL.
- VERIFIED != UNIVERSAL\_APPROVAL.
- EVIDENCE\_PACKAGE\_COMPLETE != TECHNICAL\_HOMOLOGATION.

No status transition may occur solely because a field has been populated or a producer has declared success.

## 3\. Reference framework

Reference organization: US Department of Defense.

Reference authority: DoD CIO.

Reference document: Zero Trust Execution Roadmap, version 1.1, with its exact edition metadata to be confirmed against the authoritative publication.

The seven architectural pillars are:

| Pillar | Capability IDs | Quantity |
| --- | --- | ---: |
| User | 1.1–1.9 | 9 |
| Device | 2.1–2.7 | 7 |
| Application \& Workload | 3.1–3.5 | 5 |
| Data | 4.1–4.7 | 7 |
| Network \& Environment | 5.1–5.4 | 4 |
| Automation \& Orchestration | 6.1–6.7 | 7 |
| Visibility \& Analytics | 7.1–7.6 | 6 |
| **Total** |  | **45** |

Important: the identifiers above preserve the grouping of the original XA-TRUST crosswalk. The official capability names, descriptions and expected outcomes must be transcribed and checked against the authoritative DoD source before any capability is classified as mapped or assessed.

## 4\. Mapping methodology

Each capability must have an independent record.

Required fields:

| Field | Description |
| --- | --- |
| capability\_id | Official capability identifier |
| official\_name | Exact official name |
| official\_requirement | Official expected outcome |
| xa\_component | Corresponding XA-TRUST component |
| control\_id | Identifiable control |
| implementation\_reference | Repository path and commit |
| evidence\_id | Unique evidence identifier |
| execution\_reference | Run, workflow or execution ID |
| test\_reference | Reproducible test |
| verification\_reference | Independent verifier report |
| mapping\_status | Architectural correspondence |
| implementation\_status | Implementation evidence |
| evidence\_status | Evidence lifecycle |
| limitations | Known limitations |
| assessment\_date | Assessment timestamp |

No official capability name may be invented or inferred from the XA-TRUST component name.

## 5\. Mapping status vocabulary

The following controlled values shall be used.

- NOT\_ASSESSED
- PROPOSED
- PARTIALLY\_MAPPED
- MAPPED
- IMPLEMENTATION\_NOT\_ESTABLISHED
- IMPLEMENTATION\_OBSERVED
- EVIDENCE\_PENDING
- INSUFFICIENT\_EVIDENCE
- INDEPENDENT\_VERIFICATION\_PENDING
- VERIFIED\_CLAIM\_SCOPED
- CONTRADICTED
- NOT\_APPLICABLE

A mapping marked MAPPED only indicates architectural correspondence. It does not establish implementation or compliance.

## 6\. Seven-pillar assessment

### 6.1 User

Potential XA-TRUST correspondence:

- Identity \& Policy.
- Authentication controls.
- Authorization policies.
- Identity provenance.
- Access decision traceability.

Required additional assessment:

- Identity lifecycle.
- Privileged access.
- Authentication strength.
- Continuous access evaluation.
- Identity threat detection.

### 6.2 Device

Potential correspondence:

- Device identity.
- Execution context.
- Trust boundary.
- Device-related evidence.

Required additional assessment:

- Asset inventory.
- Device health.
- Endpoint detection.
- Configuration compliance.
- Device posture evaluation.

### 6.3 Application \& Workload

Potential correspondence:

- Execution Observability.
- Workload identity.
- Decision Orchestrator.
- Application execution evidence.

Required additional assessment:

- Secure software development lifecycle.
- Application vulnerability management.
- Workload isolation.
- Runtime protection.
- Software supply-chain integrity.

### 6.4 Data

Potential correspondence:

- Evidence Collection.
- Evidence Vault.
- Custody Ledger.
- Cryptographic integrity.
- Data provenance.

Required additional assessment:

- Data classification.
- Data loss prevention.
- Data access governance.
- Encryption lifecycle.
- Data retention and disposal.

### 6.5 Network \& Environment

Potential correspondence:

- Trust Boundaries.
- Network segmentation.
- Environment identity.
- Execution isolation.

Required additional assessment:

- Network policy enforcement.
- Traffic inspection.
- Microsegmentation.
- Environment posture.

### 6.6 Automation \& Orchestration

Potential correspondence:

- Policy Engine.
- Decision Orchestrator.
- Deterministic execution.
- Policy evaluation.
- Execution evidence.

Required additional assessment:

- Automated policy enforcement.
- Workflow resilience.
- Exception management.
- Orchestration security.
- Continuous policy evaluation.

### 6.7 Visibility \& Analytics

Potential correspondence:

- Logs.
- GT7 Compliance Engine.
- GT96-R Ledger.
- Audit reports.
- Replay evidence.

Required additional assessment:

- Security information and event management.
- Threat intelligence.
- Behavioral analytics.
- Incident correlation.
- Continuous monitoring.

These are candidate correspondences, not assertions that the controls already exist or are operational.

## 7\. XA-TRUST evidence lifecycle

The following lifecycle remains frozen:

DECLARED
→ COLLECTED
→ OBSERVED
→ CRYPTOGRAPHICALLY\_BOUND
→ INDEPENDENTLY\_VERIFIED
→ CLAIM\_SCOPED\_VERIFIED
→ TECHNICALLY\_HOMOLOGATED

Every transition requires its own evidence.

No automatic promotion is permitted.

### 7.1 Evidence levels

| Level | Meaning |
| --- | --- |
| E3 | Execution evidence |
| E4 | Provenance only - who, when, where, origin. Canonical payload (RFC 8785) and hash manifest belong to E5.|
| E5 | Cryptographic binding | 
| E6 | Independent verification |
| E7 | Claim-scoped verification |
| E8 | Global-scope assessment under explicitly declared criteria |

E3–E8 are XA-TRUST evidence levels. They are not DoD Zero Trust maturity levels.


### 7.2 E7.&#32;

E7 establishes:

VERIFIED(CLAIM-X)

It does not establish universal compliance.

VERIFIED(CLAIM-X) does not imply VERIFIED(CLAIM-Y).

### 7.3 E8

E8 requires:

- Explicitly declared global assessment scope.
- Complete scope inventory.
- Independent reconstruction.
- Coverage analysis.
- Policy and control evaluation.
- Documented exclusions.
- Reproducible verification.
- Independently signed verdict.

E8 must not be inferred from the accumulation of E7 claims.

E4_PROVENANCE_RECORD.
E5_CANONICAL_PAYLOAD.
E5_HASH_MANIFEST.
E5_SIGNED_DEP.
GT7_POLICY_RESULT.
GT96R_REPLAY_REPORT.
E6_INDEPENDENT_VERIFICATION_REPORT.

### Cryptographic requirements

- Canonicalization according to RFC 8785 JCS.
- Duplicate JSON keys rejected.
- SHA-256 integrity verification.
- Ed25519 signature verification.
- Explicit signer identity and authorization evidence.
- Explicit trust boundary.
- Reproducible replay.
- Independent verification of the binding between the artifacts.

A valid hash or signature alone does not establish semantic truth, source authenticity or business correctness.

## 9\. Independent verification protocol

The producer and verifier must have separate responsibilities.

### Producer

The producer:

- Generates the execution artifacts.
- Declares execution identity.
- Supplies provenance.
- Supplies hashes and signatures.
- Publishes the declared claim scope.

### Independent verifier

The verifier:

- Retrieves the original artifacts.
- Reconstructs canonical payloads.
- Recomputes hashes.
- Checks cryptographic bindings.
- Validates provenance.
- Evaluates declared policies.
- Reproduces the relevant tests.
- Determines whether the evidence supports the claim.
- Signs its own verification report.

The producer must not generate or dictate the independent verifier's final verdict.

### Permitted verdicts

- VERIFIED
- INSUFFICIENT\_EVIDENCE
- CONTRADICTED

Every verdict must be claim-scoped and include its limitations.

## 10\. Repository deliverables

Proposed repository structure:

``` text
docs/
  XA-TRUST-DOD-CROSSWALK.md
  XA-TRUST-DOD-CROSSWALK-v2.0.md
  XA-TRUST-DOD-INDEPENDENT-VALIDATION.md

evidence/
  dod/
    DOD-45-CAPABILITY-MATRIX.csv
    DOD-CAPABILITY-SOURCE-REGISTER.json
    DOD-MAPPING-MANIFEST.json
    DOD-EVIDENCE-INDEX.json
    DOD-ASSESSMENT-REPORT.json

schemas/
  XA-TRUST-DOD-CAPABILITY-v2.schema.json
  XA-TRUST-DOD-ASSESSMENT-v2.schema.json
  XA-TRUST-DOD-VERIFICATION-v2.schema.json

tests/
  dod/
    test_capability_inventory.py
    test_mapping_completeness.py
    test_evidence_references.py
    test_scope_constraints.py
    test_verdict_separation.py
```

## 11\. Automated validation requirements

The validation pipeline must check:

1. Exactly 45 capability records.
2. Seven distinct pillar identifiers.
3. No duplicate capability IDs.
4. Official source references present.
5. Every mapping has an explicit status.
6. No MAPPED status without an architectural reference.
7. No implementation claim without implementation evidence.
8. No VERIFIED status without an independent verification report.
9. No E7 promotion without claim-scoped verification.
10. No E8 promotion without global scope and independent reconstruction.
11. No DoD certification claim without an authoritative certification source.
12. No automatic promotion from mock, simulation or pending computation.

The validator must distinguish structural validity from substantive security effectiveness.

## 12\. Acceptance criteria

The v2.0 specification may be considered structurally complete when:

- All 45 capability identifiers are accounted for.
- Official capability descriptions are source-verified.
- Every capability has a mapping record.
- Unmapped and partially mapped controls are explicitly declared.
- Evidence references are resolvable.
- Implementation claims have supporting evidence.
- The independent verification protocol is documented.
- E3–E8 scope restrictions are enforced.
- Automated structural tests pass.
- Limitations are documented.

Passing these checks does not constitute DoD certification.

## 13\. Final classification

``` yaml
document_id: XA-TRUST-DOD-CROSSWALK-SPEC-002
version: "2.0.0"
status: DRAFT
mapping_status: PROPOSED
capability_inventory: PENDING_SOURCE_VERIFICATION
implementation_coverage: NOT_ASSESSED
evidence_coverage: NOT_ASSESSED
independent_validation: PENDING
dod_maturity_level: NOT_ESTABLISHED
official_dod_approval: NOT_CLAIMED
certification: NOT_CLAIMED
technical_homologation: NOT_ESTABLISHED
```

## 14\. Governance statement

XA-TRUST provides an evidence-oriented architecture for recording, preserving, validating and independently assessing claims about digital execution and associated controls.

The DoD Zero Trust Crosswalk is an architectural mapping exerci

se.

It must not be represented as official DoD certification, accreditation, endorsement or proof of compliance.

**Final rule: A documented correspondence is a hypothesis to be assessed, not evidence of implemented security effectiveness.**

### 7\. Estado de entrega

Especificação v2.0 preparada

| Entregável                | Estado                              |
| ------------------------- | ----------------------------------- |
| Especificação técnica     | PREPARED                            |
| E3–E8                     | PRESERVED                           |
| 45 capabilities           | INVENTORY PENDING SOURCE VALIDATION |
| Independência E6          | SPECIFIED                           |
| E7 claim-scoped           | PRESERVED                           |
| E8 global scope           | SPECIFIED                           |
| Arquivos de implementação | NOT CREATED                         |
| Commit GitHub             | NOT CREATED                         |

Importante: o documento acima está preparado, mas ainda não foi gravado no repositório. Não vou atribuir um SHA de commit inexistente.

Próxima etapa recomendada: materializar a especificação, os três schemas e a matriz de 45 capabilities no repositório, em uma branch própria, preservando o commit original.