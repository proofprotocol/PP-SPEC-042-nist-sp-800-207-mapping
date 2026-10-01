# PP-SPEC-042: Proof of Efficacy Mapping to NIST SP 800-207 Zero Trust Architecture

| Field | Value |
|---|---|
| Status | DRAFT v0.1 |
| Author | Craig Ellrod, Nebulonium, Inc. (dba HACKERverse®) |
| Date | October 1, 2026 |
| License | CC BY 4.0 |
| Maps to | NIST SP 800-207 — Zero Trust Architecture |
| Series | Proof Protocol Framework Mapping Specifications |

---

## 1. Purpose

This specification defines how zero-trust principles, policy decisions, resource access, identity, and enforcement conditions can be bound to Proof Protocol test cases, evidence, and efficacy results.

The upstream source remains authoritative for its own requirements, identifiers, terminology, and guidance. This document defines a **Proof Protocol mapping** and does not supersede, reproduce, modify, or certify conformance to the upstream source.

## 2. Scope

NIST SP 800-207 supplies external context that can identify what should be examined or tested. Proof Protocol supplies an independent evidence model for determining what happened during a test and whether a selected control performed as claimed.

Independent witnessing, proof validity, evidence capture, packaging, anchoring, and efficacy semantics are defined elsewhere in the Proof Protocol specification family.

## 3. Core Question

Proof of efficacy asks:

> **Was there a control, and did it work?**

A framework requirement, criterion, principle, or obligation may identify a condition of interest. A product, architecture, policy, process, or safeguard may claim to satisfy or mitigate that condition. Proof Protocol binds the external context, test, control, observed behavior, downstream outcome, and evidence into a result that can be independently examined.

A Proof Protocol result does **not** by itself establish legal, audit, regulatory, or standards conformance unless the applicable authority separately determines that the evidence is sufficient.

## 4. Metric Definitions

Against a defined corpus or test condition, each applicable empirical case is recorded as **blocked**, **detected**, **missed**, or **INVALID** where those verdicts are meaningful.

Relevant measurements can include containment rate, detection rate, miss rate, false-positive rate, robustness under bypass or failure conditions, version-level results, and **INVALID** when required evidence is incomplete or broken.

Not every upstream requirement is empirical. Governance, documentation, organizational, legal, and procedural requirements MUST NOT be converted into efficacy scores merely because they can be referenced by a proof record.

## 5. Evidence Produced

Mapped tests can produce:

- **Proof records** binding external context, test case, control, system/version, verdict, timestamp, and evidence references;
- **ProofStamp™** trusted timestamps bound to evidence/verdict objects;
- **ProofBundle™** packages containing proof records, metrics, corpus manifests, and environment/context;
- **ProofRegister™** records for issued proof artifacts; and
- corpus and environment manifests identifying the tested conditions.

## 6. Mapping

Exact upstream identifiers and titles SHOULD be taken from the authoritative version being mapped and recorded in the ProofBundle™ where licensing permits. This specification does not redefine upstream requirements.

| External context | Proof Protocol treatment | Evidence |
|---|---|---|
| Resource/access context | Bind the protected resource, requester, requested action, and applicable policy to the test. | Test metadata |
| Policy decision | Record the authorization/policy decision separately from the resulting enforcement. | Decision evidence |
| Policy enforcement | Exercise allowed and denied actions at the relevant enforcement point. | Execution evidence |
| Identity/device context | Bind material subject, workload, device, service, and credential context. | Environment descriptor |
| Least-privilege claim | Exercise actions within and beyond asserted authorization. | Proof records |
| Downstream outcome | Determine whether the requested action actually reached or changed the protected resource. | Outcome evidence |
| Continuous evaluation | Record material policy/context changes and retest where they can affect efficacy. | Versioned proof records |

## 7. Interoperability Rules

1. The authoritative upstream source, edition/version, and applicable identifier SHOULD be recorded.
2. Upstream identifiers and terminology MUST NOT be silently redefined.
3. Proof Protocol verdicts are Proof Protocol results; they are not upstream certifications, audit opinions, legal determinations, or endorsements.
4. A control's presence, configuration, activation, detection, and efficacy are distinct facts.
5. A policy decision, alert, log entry, or control trigger does not by itself establish efficacy when the claim concerns a downstream protected outcome.
6. Target, application, tool, SIEM, vendor, service, resource, or equivalent evidence SHOULD complete the evidence round trip when required to establish the result.
7. Missing required evidence MUST yield **INVALID**, not PASS.
8. Material changes to the tested system, policy, control, environment, mapping, or corpus SHOULD trigger retesting where they can affect the result.
9. Non-empirical requirements MUST remain distinguishable from empirically tested efficacy assertions.

## 8. Framework-Agnostic Architecture

> **Threat, control, audit, and regulatory frameworks are pluggable inputs to Proof Protocol. Proof Protocol is framework-agnostic.**

External frameworks can identify **what to test or examine**. Proof Protocol independently establishes **whether the control worked and what evidence proves that result**.

No external framework is required for Proof Protocol to operate. An implementation MAY use NIST SP 800-207, another recognized framework, a proprietary threat model, several frameworks simultaneously, or no external framework when the test condition is otherwise sufficiently defined.

Adding, replacing, muting, or removing a framework mapping does not alter the Proof Protocol architecture, evidence model, Proof of Efficacy determination, ProofBundle™, ProofStamp™, ProofRegister™, or independent corroboration requirements.

A framework mapping therefore establishes **interoperability**, not architectural dependency.

## 9. Relationship to Proof Protocol

This mapping is part of the Proof Protocol specification family maintained by Nebulonium, Inc.

The relationship is intentionally asymmetric:

> **NIST SP 800-207 supplies external context. Proof Protocol supplies the evidence model for independently examining the behavior or outcome being claimed.**

No affiliation, endorsement, certification, audit opinion, or sponsorship by the upstream publisher or standards body is implied.

## 10. Source Framework, Attribution, and License

NIST SP 800-207 — Zero Trust Architecture is external work. Its names, identifiers, trademarks, normative text, and expressive content remain subject to the applicable upstream ownership and licensing terms.

This Proof Protocol mapping is independently authored and licensed under **CC BY 4.0**. That license applies only to original Proof Protocol material in this repository. It does not relicense external standards, regulations, criteria, frameworks, or trademarks.

Where upstream material is copyrighted or access-controlled, contributors MUST NOT copy protected normative text into this repository merely to make the mapping self-contained. Reference identifiers and independently authored descriptions should be used where legally appropriate.

## 11. Versioning

This mapping is versioned independently of NIST SP 800-207. Material upstream changes SHOULD trigger a mapping review and, where necessary, a new version identifying the upstream revision mapped.

---

*Proof Protocol · proofprotocol.io · CC BY 4.0*
