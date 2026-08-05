# Independent Technical Review Request

## Subject
**NDI™ Reference Architecture v2.2 — Candidate Architectural Primitive Review**

I am seeking an independent technical review of the attached public working draft.

Please assess it as though you are a senior platform architect, distinguished engineer, standards reviewer, or architecture review board member at a major cloud provider, AI infrastructure company, content-authenticity organisation, or standards body.

Please assess the architecture on technical merit rather than commercial potential. Be direct and critical. The objective is not to defend the proposal, but to identify any remaining ambiguity, architectural collapse, hidden assumption, contradiction, or unsupported claim.

Please answer the following questions:

1. Is NDI now defined as one clear, distinct architectural responsibility?
2. Does it remain meaningfully distinct from logging, timestamping, provenance, registries, and ordinary audit records?
3. Are “first observed,” “declared implementation scope,” and “neutrality” sufficiently precise and bounded?
4. Is the boundary between NDI observation and downstream chronology, verification, provenance, governance, policy, and ranking clear?
5. Are the minimum observation-record and ingress-contract concepts sufficient for a reference architecture at this stage, without over-specifying implementation?
6. Does the draft acknowledge the right threats and conformance questions? What major issue is still missing?
7. Would you recommend: reject; revise before further evaluation; continue technical evaluation; or begin early implementation/conformance work?
8. What are the three most important changes, if any, required before public publication?
9. If this arrived internally at Microsoft, Google, NVIDIA, Cloudflare, Adobe, C2PA, an IETF/W3C community, or another major infrastructure organisation, would you forward it for further technical discussion? Why or why not?

Please distinguish clearly between:
- flaws in the architectural proposition;
- missing implementation specifications;
- and matters that are appropriately deferred to later technical work.

---

# NDI™ Reference Architecture

**Version 2.2 — Public Working Draft**  
**Date:** 4 August 2026  
**Developed and published by ThopertyBox™**

> This document defines an architectural responsibility, not a complete protocol, product, implementation, legal claim, or assurance system.

---

## 1. North Star

**NDI defines one architectural responsibility:**

> **Record, without evaluative judgement, that a digital disclosure has been accepted and recorded within a declared implementation scope before downstream evaluation begins.**

NDI does not determine truth, ownership, origin, authenticity, legitimacy, reputation, policy, ranking, governance, legal priority, or trustworthiness.

It does not replace verification, provenance, attribution, moderation, compliance, or audit systems.

It establishes a scoped observation reference that those systems may later use.

> **One common starting point. Many independent paths forward.**

---

## 2. Purpose

Modern digital systems perform many important functions after information enters an environment: logging, provenance tracking, verification, policy enforcement, moderation, ranking, search, governance, compliance, identity resolution, and AI reasoning or agent action.

The architectural question addressed here is narrower:

> **Which architectural responsibility records the initial scoped observation before those downstream functions begin to evaluate, transform, classify, rank, accept, reject, or act upon the disclosure?**

NDI proposes that this responsibility should be explicit, bounded, and separable.

This document is intended to determine whether that responsibility is sufficiently distinct to justify continued technical evaluation.

---

## 3. Status and Scope of This Document

This is a **reference architecture**.

It defines:
- the responsibility of NDI;
- its boundaries and non-goals;
- the meaning of first observation within scope;
- the relationship between observation and downstream functions;
- minimum conceptual properties of an observation record;
- high-level security, conformance, and interoperability requirements.

It does not define:
- a mandatory database;
- a complete wire protocol;
- a final identifier scheme;
- a cryptographic profile;
- a consensus mechanism;
- a global clock;
- a production deployment model;
- a certification programme;
- a legal evidentiary standard;
- a commercial operating model.

Those matters belong to later protocol, implementation, conformance, governance, and legal work.

---

## 4. Core Definitions

### 4.1 Digital Disclosure

A **digital disclosure** is a digital artefact, data item, claim, payload, message, model output, or associated submission presented to an NDI implementation for observation within that implementation’s declared scope.

A disclosure may be public, private, restricted, encrypted, or access-controlled.

Observation does not, by itself, establish authorship, ownership, originality, truth, authenticity, legality, priority outside the declared scope, or permission to publish.

### 4.2 Observation Boundary

The **observation boundary** is the declared point at which an implementation accepts a disclosure for NDI recording.

The boundary must be identifiable in the implementation’s scope declaration.

It may correspond to an ingress API, edge gateway, platform upload boundary, enterprise ingestion service, consortium submission interface, archive deposit interface, or another explicitly declared acceptance point.

Events before that boundary are not NDI observations by that implementation.

### 4.3 First Observed

**First observed** means:

> the earliest successful NDI recording of a particular submitted disclosure by a particular implementation within its declared scope.

It does **not** mean first created, first published anywhere, first seen by any human, first seen across the whole internet, first globally, or first across every NDI implementation.

“First” is therefore always relative to:
1. the implementation;
2. the declared scope;
3. the observation boundary;
4. the record identity or payload binding used by that implementation.

### 4.4 Declared Implementation Scope

A **declared implementation scope** identifies the environment within which an NDI observation claim applies.

A scope declaration should identify, at minimum:
- the implementation or operator;
- the observation boundary;
- the domain or class of disclosures accepted;
- the ordering domain;
- the applicable retention or continuity commitment;
- the scope identifier and version;
- any declared eligibility rules required for safe technical operation.

Examples include one social platform, one enterprise deployment, one cloud ingestion service, one public archive, one media consortium, or one federated group of participating operators.

No implementation may infer from its own record that it possesses universal authority over observations outside its declared scope.

### 4.5 Neutrality

Within this architecture, **neutrality** is not a claim that an operator, institution, or society is free from bias.

It is a constraint on the NDI responsibility:

> **NDI does not evaluate the disclosure’s truth, quality, ownership, identity, legitimacy, policy status, ranking value, or downstream acceptability when producing the observation record.**

Neutrality is therefore defined by excluded functions and observable handling requirements, not by moral authority.

### 4.6 Evaluation

**Evaluation** includes any downstream judgement or transformation that assigns meaning, status, preference, eligibility, trust, risk, authenticity, ownership, policy treatment, ranking, or consequence to a disclosure.

NDI ends before those functions begin.

### 4.7 Observation Record

An **observation record** is the stable reference produced when an NDI implementation successfully records a disclosure within scope.

It is evidence of the implementation’s observation event, not evidence that claims within the disclosure are true.

---

## 5. The Architectural Gap

Existing systems can record events. The proposal does not deny that.

The gap is one of **primary responsibility and boundary discipline**.

In many systems, initial receipt is captured incidentally inside application logs, message queues, database timestamps, provenance stores, registration systems, moderation pipelines, analytics systems, or internal audit records.

Those systems may preserve useful evidence, but their principal responsibilities differ. They may also:
- record only after parsing or filtering;
- overwrite or aggregate events;
- apply policy before durable recording;
- use implementation-specific semantics;
- be inaccessible outside the operating platform;
- or combine observation with evaluation.

NDI proposes that scoped first observation should be an explicit architectural responsibility with its own contract, rather than an incidental side effect of another system.

---

## 6. Architectural Responsibility

NDI is responsible for:
1. receiving a disclosure at a declared observation boundary;
2. binding the observation to the submitted disclosure or a defined representation of it;
3. assigning a stable record identifier;
4. recording the event within the implementation’s ordering domain;
5. binding the record to the declared scope;
6. preserving historical continuity according to the implementation’s declared commitments;
7. returning or exposing a reference that downstream systems may use.

NDI is not responsible for deciding whether the disclosure is true, false, authentic, original, owned by the submitter, policy-compliant, rank-worthy, trustworthy, publishable, removable, or legally prior.

---

## 7. Architecture Principles

### AP-1 — Non-Evaluative Observation

An NDI implementation records the observation event without deciding the disclosure’s truth, ownership, authenticity, reputation, policy status, rank, or value.

Technical controls necessary to keep the service safe and available must not be represented as judgements about the disclosure itself.

### AP-2 — Explicit Boundary Before Downstream Evaluation

The NDI observation boundary must be identifiable.

Where an implementation performs parsing, moderation, enrichment, classification, verification, or policy evaluation, those functions must be downstream of the NDI boundary or explicitly identified as outside NDI conformance.

### AP-3 — Scope-Relative First Observation

Every first-observation claim is relative to a declared implementation scope.

NDI does not claim universal first appearance across the internet.

### AP-4 — Historical Continuity

A successful observation record is not silently rewritten to alter the original observation event.

Corrections, revocations, access changes, disputes, or later facts should be represented through linked subsequent records or other auditable mechanisms.

This principle does not require a particular storage technology and does not claim absolute immutability.

### AP-5 — Independent Implementations

Different NDI implementations may observe the same disclosure independently.

One implementation’s record does not automatically invalidate or supersede another’s.

Cross-implementation correlation may be supported through interoperable identifiers or payload bindings, but universal ordering is not assumed.

### AP-6 — Technology and Platform Independence

NDI does not mandate blockchain, distributed ledgers, a specific database, a particular cloud, a particular consensus protocol, a single timestamp authority, a programming language, or one operating organisation.

### AP-7 — Minimum Disclosure

An implementation should not require more content or identity exposure than is necessary to create and maintain the scoped observation reference.

Privacy-preserving payload binding, controlled visibility, and confidential submission are compatible with NDI.

### AP-8 — Downstream Autonomy

Downstream systems remain free to apply their own verification, provenance, governance, moderation, policy, ranking, legal, analytical, and trust decisions.

NDI seeks neither to centralise trust nor replace platform autonomy.

---

## 8. Reference Flow

```text
[ Submitter / Source / System ]
              |
              v
+------------------------------------------+
| Declared Observation Boundary            |
|                                          |
| Accept submission for NDI recording      |
| Bind disclosure to observation event     |
+--------------------+---------------------+
                     |
                     v
+------------------------------------------+
| NDI Observation Responsibility           |
|                                          |
| - assign record identifier               |
| - bind scope                              |
| - assign local sequence/order reference  |
| - record observation event               |
| - preserve continuity                    |
+--------------------+---------------------+
                     |
                     v
[ Observation Reference / Receipt ]
                     |
                     v
+------------------------------------------+
| Independent Downstream Functions         |
|                                          |
| chronology refinement · provenance       |
| verification · identity · policy         |
| moderation · ranking · compliance        |
| governance · analytics · AI processing   |
+------------------------------------------+
```

The downstream functions may accept, ignore, question, correlate, or reject the relevance of an NDI reference.

The NDI record does not dictate their conclusion.

---

## 9. The Ingress Contract

The **Ingress Contract** defines the minimum conceptual exchange at the observation boundary.

A conforming implementation should be capable of expressing, at minimum:
- `record_id` — stable identifier for the observation record;
- `scope_id` — identifier of the declared implementation scope;
- `scope_version` — version of the applicable scope declaration;
- `observation_status` — successful recording or an explicit non-recording outcome;
- `observed_at` — implementation time reference, where used;
- `sequence_reference` — local ordering or sequencing reference;
- `payload_binding` — binding to the submitted disclosure or defined representation;
- `record_created_at` — time the observation record was durably created;
- `previous_record_reference` or continuity mechanism, where applicable;
- `implementation_identifier`;
- `receipt_authentication` — implementation-defined means of validating the receipt.

A future protocol may add fields, but it must preserve the distinction between the observation event, claims made by the submitter, and downstream evaluative conclusions.

### 9.1 Payload Binding

Payload binding allows an implementation to associate the record with the disclosure without necessarily exposing the content publicly.

Possible implementations include hashes, commitments, content-addressed identifiers, encrypted references, or other techniques.

This architecture does not select a final mechanism.

A payload binding proves only that the implementation associated its observation record with a defined representation. It does not prove authorship, ownership, truth, or legality.

---

## 10. NDI and Chronology

NDI records an observation event and provides enough ordering information for that event to be placed within the implementation’s local ordering domain.

A separate chronology function may later compare multiple records, reconcile clocks, correlate observations across scopes, construct timelines, or apply stronger ordering semantics.

Where the term **NCO™ — Neutral Chronological Orientation** is used in the wider ThopertyBox framework:
- **NDI** owns the scoped observation event and its receipt;
- **NCO** owns extended chronological orientation across records or environments.

NDI must not be described as establishing a universal chronology.

---

## 11. Comparison with Adjacent Categories

### 11.1 NDI vs Logging

A log records operational events for purposes such as debugging, observability, monitoring, security, or audit.

A log may capture receipt of a disclosure, but usually as one event among many and according to the emitting system’s internal needs.

NDI differs because scoped first observation is its primary architectural responsibility.

A general log can be used to implement part of NDI only if it also satisfies the NDI boundary, scope, continuity, non-evaluation, record, and conformance requirements.

### 11.2 NDI vs Timestamping

Timestamping binds a time value or time assertion to data.

NDI may use timestamps, but its responsibility is broader and more specific: it records a scoped observation event, binds it to a declared scope and disclosure representation, and produces a stable reference.

A timestamp alone does not define the observation boundary, scope, non-evaluation contract, or record semantics.

### 11.3 NDI vs Provenance

Provenance describes origin claims, derivation, custody, transformation, editing, or history.

NDI does not establish those facts.

An NDI record may become one event within a provenance history, but it only states that a particular implementation observed a defined disclosure within scope.

Provenance explains the trail. NDI anchors one scoped point at which that trail may be observed.

### 11.4 NDI vs Registries

A registry maintains entries for administration, discovery, rights, identity, inventory, or publication.

A registry may contain NDI records, but registration usually carries domain-specific semantics.

NDI does not manage the full status or lifecycle of a registered entity. It records the scoped observation event.

### 11.5 NDI vs Audit Records

Audit records support accountability and later review of actions or controls.

NDI records may support audit, but NDI is positioned at the observation boundary and deliberately excludes the wider judgement and accountability functions of an audit system.

---

## 12. Neutrality and Conformance

Neutrality cannot be established by branding or self-description alone.

A future conformance profile should define observable tests.

Candidate conformance requirements include:

1. **Boundary test** — demonstrate that a successful record is created at the declared observation boundary before specified downstream evaluative functions.
2. **Non-evaluation test** — demonstrate that receipt generation does not depend on truth, ownership, popularity, reputation, ranking, or policy conclusions.
3. **Duplicate test** — disclose how repeated or identical submissions are handled. Deduplication must not silently erase evidence that multiple submission events occurred.
4. **Suppression test** — identify all conditions under which a submission is not recorded and produce an explicit non-recording outcome where safe and appropriate.
5. **Continuity test** — demonstrate that a previously issued record is not silently rewritten to change the original observation event.
6. **Scope test** — demonstrate that every receipt identifies the applicable scope and does not imply authority beyond it.
7. **Ordering test** — demonstrate consistent behaviour of the local sequence or ordering reference under concurrent submissions.
8. **Black-box behaviour test** — submit controlled inputs that differ only in evaluative attributes and test whether receipt behaviour improperly varies.

These tests do not prove that an operator is free from all hidden misconduct. They create falsifiable requirements and auditable evidence.

---

## 13. Eligibility, Safety Controls, and the Pre-Observation Boundary

A real implementation may require technical controls to remain safe, lawful, and available.

Examples include protocol validation, maximum payload sizes, malware containment, rate limits, authentication for restricted services, duplicate transport suppression, denial-of-service protection, and legally required access restrictions.

These controls do not automatically violate neutrality.

However:
1. they must be declared;
2. they must be limited to operational necessity;
3. they must not be misrepresented as NDI judgements about truth or value;
4. they should produce auditable outcomes;
5. they must not silently move substantive evaluation ahead of the declared observation boundary.

A future conformance profile must distinguish **technical admissibility** from **evaluative eligibility**.

Only the former may occur as an NDI-adjacent safety control.

---

## 14. Ordering and Time Model

NDI does not assume that wall-clock time alone is sufficient.

A robust implementation may combine implementation timestamps, monotonic counters, sequence numbers, append positions, trusted time services, cryptographic chaining, distributed ordering mechanisms, or other methods.

The architecture requires that the implementation declare:
- what its time value means;
- what its sequence reference means;
- the ordering guarantees it provides;
- known clock-skew limitations;
- whether ordering applies to one node, one service, one region, or the whole declared scope.

NDI does not require a total global order across independent implementations.

---

## 15. Duplicate and Repeated Disclosures

A repeated disclosure may represent a transport retry, duplicate submission, second actor submitting identical content, the same actor resubmitting, or a genuinely distinct event with the same payload.

An NDI implementation must not treat identical payloads as proof that the events are identical.

A future protocol should distinguish:
- **payload identity**;
- **submission-event identity**;
- **observation-record identity**.

Implementations may optimise storage, but they should preserve an auditable representation of distinct successful observation events.

---

## 16. Visibility and Privacy

NDI records that a disclosure was observed. It does not require the content itself to be public.

Implementations may support public receipts, private receipts, encrypted disclosures, restricted verification, delayed publication, selective disclosure, confidential enterprise use, and protected creator or innovator submissions.

Public visibility of a receipt does not imply public visibility of the underlying content.

Privacy and access-control decisions must not alter the original fact of the scoped observation event.

---

## 17. Threat Considerations

This section identifies threats that future specifications and implementations must address. It is not a complete threat model.

### 17.1 Predating and Backdating
An operator may attempt to assign an earlier time or sequence position than the actual observation event.

### 17.2 Reordering
Concurrent or distributed submissions may be reordered accidentally or deliberately.

### 17.3 Replay
An attacker may resubmit an old disclosure or receipt.

### 17.4 Suppression
An operator may fail to record, hide, delay, or selectively discard submissions.

### 17.5 Selective Neutrality
An implementation may claim neutrality while applying hidden content, identity, or reputation filters before recording.

### 17.6 Operator Compromise
An attacker or insider may manipulate records, keys, sequence state, or interfaces.

### 17.7 Flooding and Resource Exhaustion
A neutral observation endpoint may be abused for denial of service or storage exhaustion.

### 17.8 Payload-Binding Attacks
Weak or ambiguous payload representation may create collisions, canonicalisation disputes, or misleading equivalence.

### 17.9 Scope Misrepresentation
An implementation may imply that a local observation is global or authoritative outside its scope.

### 17.10 Privacy Leakage
Metadata, timing, identifiers, or public queries may expose confidential activity.

Mitigations belong to later security and implementation profiles, but must include declared controls, auditability, recovery, key management, rate protection, binding rules, scope visibility, and privacy analysis.

---

## 18. Interoperability Direction

Two independent implementations should be able to exchange or compare observation references without assuming shared governance.

A future interoperability profile should define:
- common record representation;
- scope identifiers;
- payload-binding profiles;
- receipt validation;
- versioning;
- error and rejection semantics;
- cross-scope correlation;
- privacy-preserving comparison;
- conformance claims.

Interoperability does not require a single operator or global database.

---

## 19. Relationship to Existing Architectures

NDI is intended to complement, not replace:
- C2PA and Content Credentials;
- W3C provenance models;
- transparency logs;
- trusted timestamping;
- digital identity;
- evidence and audit systems;
- content moderation;
- platform logging;
- data lineage;
- AI governance;
- compliance tooling.

A provenance system may consume an NDI observation as an early event.

A transparency system may publish or anchor NDI records.

An audit system may test NDI conformance.

A platform may implement NDI at an ingress boundary while retaining all existing internal logs and controls.

NDI is not a claim that these systems are inadequate. It asks whether scoped non-evaluative first observation should be made explicit before they begin their own responsibilities.

---

## 20. Relationship to AI Systems

AI systems increasingly ingest, retrieve, transform, rank, and act upon external data.

An NDI implementation may be placed before model-training data ingestion, retrieval-augmented generation pipelines, autonomous agent tool ingestion, model-output publication, enterprise AI knowledge ingestion, content moderation and ranking, or synthetic-media distribution.

The NDI reference states what the implementation observed within scope before downstream AI processing.

It does not establish that the material is safe, licensed, correct, representative, or suitable for training.

Possible compute, reconciliation, or workflow savings are hypotheses for empirical evaluation, not claims established by this architecture.

---

## 21. Relationship to ThopertyBox™

NDI is application-neutral.

ThopertyBox is a separate reference ecosystem that may implement the NDI responsibility as one part of a wider governed discovery workflow.

In that possible implementation, participants may submit a controlled disclosure, receive an observation reference, keep the disclosure private, develop it further, seek collaborators, investors, manufacturers, or partners, or later make it publicly discoverable through other services.

That ecosystem is one possible implementation above NDI.

It does not define the only valid use of NDI.

A news agency, AI company, archive, enterprise CMS, media marketplace, social platform, cloud provider, or government body could implement the same architectural responsibility with entirely different products and workflows.

---

## 22. Stewardship and Platform Autonomy

NDI seeks neither to centralise trust nor replace platform autonomy.

Any organisation may implement the responsibility while preserving independence over its products, policies, governance, moderation, ranking, legal obligations, commercial services, and technical choices.

Long-term stewardship may be undertaken by an independent standards body, multi-stakeholder foundation, consortium, public-interest institution, or one or more interoperable operators.

This document does not prescribe the final stewardship model.

Architectural separation is more important than ownership alone.

---

## 23. Example Scenarios

### 23.1 AI-Generated Media
A platform receives an AI-generated video. NDI records the scoped observation event at the declared ingress boundary. Downstream systems inspect Content Credentials, verify signatures, classify synthetic content, apply policy, and rank or remove the item.

### 23.2 Courtroom or Evidential Dispute
An NDI record may show that one implementation observed a bound representation at a particular scoped sequence and time reference. A court or expert must still determine admissibility, authenticity, chain of custody, relevance, and legal effect.

### 23.3 Creator-Controlled Disclosure
A creator submits an unpublished design to a controlled service. The service creates a private NDI observation receipt. The creator later chooses whether to disclose the content publicly, seek partners, or retain confidentiality.

### 23.4 Cross-Platform Media Distribution
A news organisation distributes the same media object to several platforms. Each platform may generate its own NDI observation record. The records may be compared through payload bindings without claiming one universal global first observation.

### 23.5 Removed Platform Content
A platform removes content under its own policy. The NDI record may remain as a reference that the platform observed a bound disclosure at a particular point, subject to privacy and legal constraints. The record does not prevent removal and does not expose the content by default.

---

## 24. Claims This Architecture Does Not Make

This document does not claim that NDI:
- proves truth;
- proves ownership;
- establishes global first publication;
- prevents all censorship;
- eliminates operator misconduct;
- replaces provenance;
- replaces platform logs;
- is automatically legally admissible;
- is already a standard;
- is already implemented at internet scale;
- guarantees compute or energy savings;
- is immune to governance failure;
- requires public disclosure;
- requires centralised control.

---

## 25. Evaluation Criteria for the Candidate Primitive

NDI should continue to be treated as a distinct architectural primitive only if technical review supports all of the following:

1. The responsibility is coherent and bounded.
2. Existing categories do not already cover it sufficiently as a primary responsibility.
3. The non-evaluation boundary can be made observable and testable.
4. The ingress contract can be implemented without unacceptable latency or operational burden.
5. Scope-relative claims can interoperate without implying global authority.
6. The threat model can be addressed with credible controls.
7. At least two independent implementations could conform without relying on one operator’s private semantics.

If these conditions cannot be met, NDI should be collapsed into an existing category rather than maintained as a separate primitive.

---

## 26. Future Work

If continued evaluation is recommended, the next technical work should include:
1. a formal observation-record schema;
2. a minimal protocol and API profile;
3. a conformance test suite;
4. a complete threat model;
5. a privacy model;
6. payload canonicalisation and binding profiles;
7. ordering and clock profiles;
8. a minimal reference implementation;
9. two independent interoperability demonstrations;
10. performance, latency, storage, and cost testing;
11. governance and stewardship options;
12. legal and evidentiary analysis by qualified specialists.

---

## 27. Invitation to Technical Review

This architecture has been refined through repeated critical review.

The objective has not been to collect agreement.

It has been to expose ambiguity, narrow claims, strengthen boundaries, separate architecture from implementation, and identify what must still be proven.

The central question is:

> **Does scoped, non-evaluative first observation constitute a sufficiently distinct architectural responsibility to justify further implementation, conformance, and standards work?**

---

## 28. Conclusion

NDI proposes one bounded responsibility:

> **Record that a digital disclosure was accepted and recorded within a declared implementation scope before downstream evaluation begins.**

It provides a reference, not a verdict.

It preserves platform autonomy.

It does not centralise truth.

It does not replace provenance, verification, governance, or policy.

Its value, if established, would come from making the earliest observation boundary explicit, interoperable, and testable.

Whether that responsibility should become part of future digital and AI infrastructure is now a matter for technical evaluation.

---

## Version History

- **v2.2 — 4 August 2026**  
  Tightened first-observation semantics; formalised declared implementation scope; added ingress contract, adjacent-category comparison, conformance direction, ordering model, duplicate handling, privacy, threat considerations, interoperability direction, NDI/NCO boundary, and explicit claims not made.

- **v2.1 — July 2026**  
  Established NDI as a distinct candidate architectural responsibility and strengthened scope and non-goals.

---

© 2026 ThopertyBox™  
NDI™ is an architectural concept developed by ThopertyBox™.  
Public Working Draft for technical review.
