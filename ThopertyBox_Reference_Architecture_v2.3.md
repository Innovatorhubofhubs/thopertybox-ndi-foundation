
NDI™ Reference Architecture v2.3 

Candidate Public Working Draft

Status

This document defines a candidate reference architecture for NDI™ — Neutral Discovery Infrastructure.

NDI is presented for independent technical review as a proposed architectural responsibility. It is not presented as a finished standard, product specification, compliance mechanism, or claim of technical novelty in its underlying cryptographic components.

The purpose of v2.3 is narrower:

«To determine whether neutral, scope-declared observation before downstream evaluation merits recognition as a distinct architectural responsibility.»

---

1. North Star

Digital information increasingly passes through systems that classify, transform, rank, verify, moderate, attribute, recommend, govern, or amplify it.

Those functions may be necessary and valuable.

But each occurs after an observation has entered a system boundary.

NDI proposes that the observation itself can be treated as a distinct architectural responsibility:

«Establish a neutral, scope-bounded reference to a qualifying digital observation before downstream systems determine what that observation means.»

NDI does not establish universal origin.

It establishes a reference to an observation made within a declared implementation scope and ordering domain.

This distinction is fundamental.

---

2. The Architectural Question

Existing architectures provide mature mechanisms for:

- logging;
- trusted timestamping;
- transparency;
- provenance;
- authentication;
- registries;
- audit;
- content integrity;
- policy enforcement; and
- verification.

NDI does not propose to replace these mechanisms.

Its architectural question is different:

«Should the act of recording a qualifying observation, within an explicitly declared scope and before downstream evaluation, exist as a separately defined responsibility?»

If that responsibility is already fully satisfied by an existing architecture, NDI may be unnecessary.

If it is not, NDI proposes a bounded contract for that responsibility.

---

3. Core Responsibility

An NDI-conforming implementation records a qualifying observation event occurring at a declared observation boundary.

The resulting observation record provides a persistent reference to:

- what representation was observed;
- within which declared scope;
- at which observation boundary;
- according to which ordering domain;
- under which scope and recording-policy version; and
- where that event sits within the implementation's defined record sequence.

NDI does not require that the observation subsequently be judged correct, authentic, lawful, original, trustworthy, important, or unique.

Its responsibility ends with the neutral observation reference.

---

4. What “First Observed” Means

Earlier NDI drafts used “first observed” as shorthand.

v2.3 explicitly bounds that term.

Within NDI:

«“First observed” means the earliest qualifying observation represented by an NDI implementation within its declared observation scope and according to its declared ordering semantics.»

It does not mean:

- first existence anywhere;
- first creation;
- first publication globally;
- first observation by another implementation;
- first observation outside the declared scope;
- proof of authorship;
- proof of ownership; or
- legal priority.

An earlier observation or earlier evidence may exist elsewhere.

NDI neither denies nor adjudicates that possibility.

Where ambiguity could arise, implementations SHOULD prefer the explicit expression:

“earliest qualifying observation recorded within declared scope.”

---

5. Declared Implementation Scope

Every NDI implementation MUST declare the scope within which its observation claims apply.

A scope declaration MUST make discoverable, at minimum:

- the implementation or operator responsible for the scope;
- the observation boundary;
- the categories or sources eligible for observation;
- relevant admission or exclusion conditions;
- the applicable ordering domain;
- the scope/version identifier;
- material pre-observation filtering conditions;
- the applicable retention or continuity commitment; and
- limitations affecting interpretation of the record.

Scope is not a claim of completeness beyond the declared boundary.

An NDI implementation MUST NOT imply that absence from its records establishes absence outside its scope.

---

6. Observation Boundary

The observation boundary defines the point at which an event becomes eligible to create an NDI observation record.

This boundary is critical because neutrality cannot be claimed over information the implementation never had an opportunity to observe.

Therefore:

«NDI can make claims only about events that reach its declared observation boundary.»

Filtering, moderation, admission control, crawler selection, access restrictions, technical failure, or other processes occurring before that boundary may affect what becomes observable.

Where such processes materially constrain observation, their existence MUST be represented in the scope declaration or associated policy.

An implementation MUST NOT describe material excluded before the observation boundary as though NDI neutrally observed and rejected it.

---

7. Qualifying Observation Event

A qualifying observation event occurs when information satisfying the declared ingress conditions reaches the observation boundary and the implementation creates the corresponding observation record.

The architecture distinguishes:

observation from submission.

A submission may be one mechanism by which an observation occurs, but NDI does not require all observations to originate through user submission.

Depending on implementation scope, observation may occur through an API, platform boundary, controlled intake, automated discovery mechanism, system event, or another explicitly declared process.

The mechanism MUST NOT change the semantic meaning of the resulting record:

«the implementation observed the represented disclosure within the declared scope under the declared conditions.»

---

8. Minimum Observation Record

A conforming observation record MUST contain, or provide a verifiable reference to, sufficient information to establish:

1. Record identifier
   A unique reference for the observation record.

2. Payload or representation binding
   A mechanism binding the record to the representation observed, without requiring NDI to interpret its meaning.

3. Scope reference
   The declared scope and applicable scope version.

4. Observation boundary reference
   The boundary or ingress context at which the qualifying observation occurred.

5. Ordering information
   Information sufficient to determine the event's position according to the implementation's declared ordering semantics.

6. Time information
   Any time assertion made by the implementation, with its semantics and limitations distinguishable from logical sequence ordering.

7. Record integrity information
   Sufficient information to support detection of unauthorised retrospective alteration according to the implementation's conformance model.

Additional metadata MAY be provided, provided it does not alter NDI's core non-evaluative responsibility.

---

9. Time and Ordering

NDI does not assume that wall-clock timestamps alone establish authoritative ordering.

A conforming implementation MUST define the ordering semantics applicable within its scope.

It MUST distinguish, where applicable, between:

- wall-clock time;
- observation time;
- record-creation time;
- sequence position;
- externally witnessed or trusted time; and
- other ordering assertions.

Clock skew, backdating, replay, delayed ingestion, network partition and related conditions MUST NOT be concealed behind an unsupported claim of universal chronological certainty.

NDI establishes only the ordering properties its implementation can demonstrate.

---

10. Duplicate and Replay Handling

A conforming implementation MUST define its behaviour when:

- the same representation is observed repeatedly;
- equivalent content appears through different representations;
- a previously recorded event is replayed;
- the same disclosure is observed through different ingress paths; or
- observations occur concurrently or cannot be deterministically ordered.

NDI does not require semantic deduplication.

Where equivalence cannot be established without interpretation, records MAY remain independently represented.

An implementation MUST NOT silently convert uncertain equivalence into a claim of identical origin.

---

11. Neutrality

Within NDI, neutrality is an architectural constraint, not a claim that an operator has no interests, policies, or biases.

Neutrality means that the NDI observation responsibility itself does not determine:

- truth;
- authenticity;
- authorship;
- ownership;
- originality;
- legal entitlement;
- provenance;
- trustworthiness;
- ranking;
- policy compliance;
- reputational value; or
- downstream action.

These determinations may be performed by other systems.

They are outside the NDI responsibility.

Neutrality therefore arises primarily through separation and exclusion of evaluative functions, rather than through a claim that every implementation observes everything.

---

12. Explicit Non-Claims

An NDI observation record MUST NOT, solely by virtue of its existence, be interpreted as evidence that:

- the observer or submitter created the material;
- the observer or submitter owns the material;
- the material is original;
- the material is authentic;
- the material is true;
- the material is lawful;
- the material was authorised for disclosure;
- the observation represents the first occurrence globally;
- the observation establishes legal priority; or
- the material should be trusted, promoted, removed, ranked, or otherwise acted upon.

An earlier NDI record is an earlier recorded observation within the applicable scope and ordering domain.

It is not a verdict about priority of creation or entitlement.

This limitation is part of NDI's architecture, not merely a legal disclaimer.

---

13. Integrity and Record Continuity

NDI does not require one prescribed cryptographic implementation.

A conforming implementation MUST, however, provide mechanisms appropriate to its claimed conformance level for detecting unauthorised retrospective:

- alteration;
- insertion;
- deletion;
- substitution; or
- reordering

of observation records.

Implementations MAY use append-only logs, cryptographic commitments, signatures, externally witnessed state, transparency mechanisms, or other suitable techniques.

NDI specifies the required architectural property rather than mandating a particular implementation primitive.

Absolute immutability is not assumed.

---

14. Failure, Suppression and Omission

NDI cannot record what its declared observation boundary does not observe.

Potential failure conditions include:

- intentional suppression;
- pre-boundary filtering;
- unavailable sources;
- access restrictions;
- implementation outage;
- ingestion failure;
- clock manipulation;
- record replay;
- delayed recording;
- operator compromise; and
- selective retention.

A conforming implementation MUST document material failure modes relevant to its claimed scope.

Where a failure is detectable, the architecture SHOULD support representation of that condition without converting it into a judgment about the underlying disclosure.

Absence of a record MUST NOT be treated as proof that an event did not occur.

---

15. Relationship to Timestamping

Trusted timestamping can establish evidence that particular data existed at or before a stated time.

NDI may use timestamping mechanisms, but timestamping alone does not define NDI.

NDI additionally defines:

- a declared observation boundary;
- a qualifying observation event;
- scope semantics;
- an ordering domain;
- explicit separation from downstream evaluation;
- observation-record semantics; and
- mandatory non-claims.

The architectural distinction is therefore not a novel timestamping mechanism.

It is the proposed responsibility contract surrounding the observation event.

---

16. Relationship to Transparency Logs

Transparency logs provide important precedent for append-only, auditable and verifiable record structures.

NDI may be implemented using transparency-log techniques.

However, NDI is not defined by a particular log technology or application domain.

NDI's proposition is that a transparency mechanism MAY satisfy the NDI responsibility where it also satisfies the required observation-boundary, scope, record-semantic, neutrality and conformance properties.

NDI therefore does not require existing infrastructure to be replaced merely because it predates NDI.

An existing system could potentially be NDI-conforming if it satisfies the defined architectural contract.

---

17. Relationship to Provenance and C2PA

Provenance architectures can describe origin claims, actors, transformations, credentials and the history of digital content.

NDI deliberately stops earlier.

A simplified distinction is:

«NDI establishes a scoped observation reference. Provenance systems may subsequently describe the trail.»

NDI does not compete with or replace provenance standards such as C2PA.

A downstream provenance system MAY reference an NDI observation record where useful, but such integration is outside the core NDI responsibility.

---

18. Relationship to Logging, Audit and Registries

Ordinary system logging generally records events relevant to operation of a particular system.

Audit systems record information required for later examination or accountability.

Registries maintain structured records about defined entities or claims.

NDI may use mechanisms common to all three.

Its proposed distinction is not the storage mechanism but the explicitly separated responsibility to record a qualifying observation at a declared boundary without importing downstream evaluative claims into that observation record.

If an existing logging, audit, or registry architecture satisfies that responsibility and the NDI conformance contract, NDI does not require duplication of the underlying mechanism.

---

19. Architectural Independence

NDI is defined independently of any specific:

- commercial platform;
- AI model;
- provenance provider;
- blockchain;
- timestamp authority;
- identity provider;
- government;
- standards organisation; or
- ThopertyBox™ implementation.

Architectural independence does not imply operational independence from every dependency.

A conforming implementation MUST disclose material dependencies relevant to verification of its observation records.

---

20. Downstream Separation

After an NDI observation record exists, downstream systems may:

- verify;
- authenticate;
- attribute;
- establish provenance;
- rank;
- moderate;
- govern;
- investigate;
- compare;
- audit;
- recommend; or
- otherwise interpret the observation.

Those activities do not retroactively change what the NDI observation record asserts.

They may add new information, challenge assumptions, discover earlier evidence, or reach conflicting conclusions.

NDI preserves the bounded observation reference while allowing those downstream systems to remain independent.

---

21. Conformance

An implementation claiming NDI conformance MUST, at minimum:

1. declare its implementation scope;
2. identify its observation boundary;
3. define what constitutes a qualifying observation;
4. bind records to the observed representation;
5. define applicable ordering semantics;
6. distinguish ordering from unsupported wall-clock certainty;
7. define duplicate/replay behaviour;
8. provide mechanisms for detecting unauthorised retrospective record alteration appropriate to its conformance claim;
9. disclose material pre-observation filtering or admission constraints;
10. publish the semantics of its observation records;
11. preserve the explicit NDI non-claims; and
12. maintain separation between observation and downstream evaluative functions.

Conformance does not require identical implementations.

Different implementations MAY use different technical mechanisms while satisfying the same architectural responsibility.

---

22. Security Considerations

NDI does not eliminate adversarial behaviour.

Relevant threats include:

- malicious or unauthorised submissions;
- copied-content front-running;
- replay attacks;
- timestamp manipulation;
- record insertion or suppression;
- split-view or inconsistent record presentation;
- pre-boundary filtering;
- denial of observation;
- scope misrepresentation;
- operator compromise;
- misleading downstream interpretation; and
- attempts to present an observation record as proof of ownership, originality, authenticity, or truth.

A neutral record of malicious or copied material remains a valid record of the observation event.

It does not legitimise the material.

Implementations MUST therefore preserve the distinction between record validity and content validity.

---

23. What NDI Does Not Attempt to Solve

NDI does not attempt to solve:

- global firstness;
- universal ordering across independent scopes;
- authorship;
- ownership;
- originality;
- truth;
- authenticity;
- content safety;
- copyright or patent priority;
- identity;
- provenance;
- platform governance;
- regulatory compliance;
- ranking;
- moderation; or
- universal trust.

These may be legitimate downstream responsibilities.

Adding them to NDI would change the responsibility being proposed.

---

24. Deployment and Adoption Are Separate Questions

This reference architecture defines a responsibility.

It does not predict that creators, organisations, platforms, governments, or AI systems will adopt it.

Potential workflows—including establishing an observation reference before wider disclosure—are deployment and adoption hypotheses, not properties guaranteed by NDI.

Such hypotheses require separate technical, economic, behavioural, governance and legal evaluation.

They are intentionally excluded from the core architectural definition.

---

25. Relationship to ThopertyBox™

NDI originated within the broader ThopertyBox™ work.

The NDI reference architecture is intentionally separated from that commercial and product context.

A ThopertyBox implementation MAY use NDI.

NDI does not require ThopertyBox, and an NDI-conforming implementation need not have any relationship with ThopertyBox.

This separation is necessary for NDI to be evaluated on architectural merit rather than commercial ownership or product strategy.

---

26. North Star Restated

NDI does not ask downstream systems to agree.

It does not ask one observer to determine universal origin.

It does not replace provenance, verification, audit, governance, policy, or trust.

It proposes something smaller:

«Preserve a neutral, scope-bounded reference to the qualifying observation before downstream interpretation begins.»

One reference responsibility.

Many independent paths may follow.

---

27. Invitation to Technical Review

NDI v2.3 is presented as a candidate architectural responsibility, not a completed standard.

Review is specifically invited on the following questions:

1. Is the NDI observation responsibility sufficiently distinct from ordinary timestamping, transparency logging, audit, registries, archiving, and provenance?

2. Are the observation boundary, qualifying observation event, declared scope, and ordering domain sufficiently precise to support independent implementation?

3. Does the architecture successfully prevent scoped observation from being misinterpreted as global firstness, authorship, ownership, originality, authenticity, or truth?

4. Is neutrality adequately expressed as architectural separation and exclusion rather than as an unsupported claim about operator behaviour?

5. Are the minimum observation-record and conformance requirements sufficient without prematurely prescribing implementation mechanisms?

6. Are pre-boundary filtering, suppression, replay, ordering manipulation, duplicate handling, front-running, and operator compromise adequately recognised?

7. Could existing infrastructure satisfy this responsibility through an NDI conformance profile, or does the proposed responsibility collapse into an already-established architectural category?

8. Is there any material architectural defect that should prevent this candidate from proceeding to serious human technical review?

---

Closing Principle

Before AI amplifies it, NDI anchors it.

Within this architecture, anchors means establishing and preserving a neutral, scope-bounded observation reference.

It does not mean proving origin, ownership, truth, or universal firstness.

That distinction is intentional.
