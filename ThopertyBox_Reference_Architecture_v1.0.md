

NDI™ Reference Architecture
Public Working Draft v2.1 (Review Candidate)
North Star
Scope
This document defines a single architectural responsibility.
It does not define a complete implementation, protocol, governance framework or technical standard.
Its purpose is to establish the architectural boundaries, principles and responsibilities required for further technical discussion.
Terminology
Digital disclosure — The event in which digital information first becomes observable within an implementation's declared implementation scope.
First observed — The earliest observation made by a specific NDI implementation within its declared implementation scope. This does not imply the earliest occurrence across all implementations or across the Internet.
Declared implementation scope — The explicit boundary within which an NDI implementation records observations and to which its chronological guarantees apply.
Architectural Responsibility
NDI™ (Neutral Discovery Infrastructure) defines one architectural responsibility:
To record neutrally when a digital disclosure is first observed within its declared implementation scope.
NDI neither determines nor evaluates truth, ownership, provenance, authenticity, trust, policy, ranking or governance.
It does not replace verification, attribution, provenance or compliance. Rather, it provides a neutral chronological reference upon which those independent responsibilities may operate.
By separating neutral chronological observation from all downstream evaluation and decision-making, NDI establishes a common reference that other systems may use according to their own responsibilities.
One common starting point. Many independent paths forward.
The Architectural Gap
The Internet has evolved specialised architectural responsibilities for networking, storage, identity, security, search, provenance, governance and artificial intelligence.
Each addresses a distinct responsibility within the wider digital ecosystem.
As AI systems increasingly discover, interpret and act upon digital information, an architectural question emerges that is not explicitly addressed by those existing responsibilities.
What neutral architectural responsibility records when a digital disclosure is first observed before downstream systems begin evaluating, interpreting or acting upon it?
Existing technologies already provide essential capabilities including identity, provenance, verification, governance and search.
NDI does not seek to replace any of those capabilities.
Instead, it proposes one additional architectural responsibility:
The neutral chronological recording of when a digital disclosure is first observed within a declared implementation scope.
This proposal argues that defining this responsibility separately allows downstream systems to operate from a shared chronological reference while preserving a clear separation of architectural concerns.
Why This Responsibility Matters
Every digital system begins with an input.
Every search engine, provenance framework, governance process and AI model ultimately depends upon information entering its environment before any downstream processing occurs.
As artificial intelligence becomes increasingly autonomous in discovering, interpreting and acting upon digital information, the integrity of that starting point becomes increasingly significant.
The question is no longer simply:
"What can AI do?"
Increasingly, it becomes:
"What is AI acting upon?"
Existing architectural layers already provide essential capabilities for verification, attribution, provenance, governance and policy.
Those responsibilities remain unchanged.
NDI proposes something different.
It introduces a neutral chronological reference that exists before those downstream responsibilities begin.
By establishing a neutral point of first observation within a declared implementation scope, NDI provides a common chronological reference that independent systems may choose to use according to their own requirements.
The value of that reference is not determined by NDI itself.
It is determined by the systems that choose to build upon it.
What NDI Is
NDI™ (Neutral Discovery Infrastructure) is a proposed reference architecture that defines one narrowly scoped architectural responsibility:
To record neutrally when a digital disclosure is first observed within its declared implementation scope.
The architecture is intentionally narrow in scope.
It defines a responsibility rather than a product, platform, service or governing authority.
NDI records that a digital disclosure has been observed. It does not determine what the disclosure means, whether it is true, who owns it, or how it should be interpreted or governed.
By deliberately separating neutral chronological recording from all subsequent evaluation, NDI provides a common architectural reference that independent downstream systems may use according to their own responsibilities.
Architectural Independence
For the purposes of this reference architecture, architectural independence refers to the separation of responsibilities rather than the ownership or governance of any implementation.
NDI operates independently of the policies, commercial objectives and decision-making processes of downstream systems.
It neither prescribes nor depends upon how other systems verify, rank, govern, moderate or interpret recorded disclosures.
This document defines only the architectural responsibility itself.
It does not prescribe future ownership, stewardship, governance or commercial implementation.
What NDI Is Not
NDI intentionally defines one architectural responsibility and deliberately excludes responsibilities that belong elsewhere.
NDI is not:
A search engine
An AI model
A provenance framework
An identity system
A verification service
A governance framework
A compliance framework
A ranking algorithm
A trust engine
A content moderation system
A blockchain or distributed ledger
Likewise, NDI does not determine:
Truth
Ownership
Authenticity
Legality
Reputation
Importance
Quality
Intent
Policy
Trust
These responsibilities remain with independent downstream systems.
NDI's responsibility ends where theirs begins.
Architectural Principles
This reference architecture is defined by a small number of principles that describe the responsibility itself rather than any specific implementation.
AP-1 — Neutrality
NDI records digital disclosures without making evaluative judgements.
It neither promotes nor suppresses information, and it does not assess truth, ownership, authenticity, value or trust.
AP-2 — Chronological Integrity
NDI preserves the chronological order in which digital disclosures are first observed within its declared implementation scope.
Chronological recording remains independent of popularity, payment, optimisation or subsequent interpretation.
AP-3 — Separation of Responsibilities
NDI records.
Other systems verify.
Other systems attribute.
Other systems govern.
Other systems rank.
Other systems interpret.
Maintaining this separation is fundamental to the architecture.
AP-4 — Implementation Independence
This reference architecture defines a responsibility rather than a single implementation.
Different organisations may implement NDI using different technologies, provided the architectural responsibility and principles remain intact.
AP-5 — Declared Implementation Scope
Every implementation operates within a clearly declared implementation scope.
NDI makes no claim to record every digital disclosure across the Internet.
Its chronological guarantees apply only within the scope declared by the implementation.
For example, two independent NDI implementations may observe the same digital disclosure within their respective declared scopes. Each records that observation independently. Neither implementation supersedes the other outside its own declared scope.
Reference Architecture
NDI defines one architectural responsibility:
To record neutrally when a digital disclosure is first observed within its declared implementation scope.
That responsibility may be implemented using different technologies and deployment models, but every implementation remains faithful to the same sequence of responsibilities.
Stage 1 — Disclosure
A digital disclosure is presented within the declared implementation scope.
At this stage, NDI is concerned only with the observation of that disclosure.
It makes no judgement regarding its meaning, quality, ownership, authenticity or value.
Stage 2 — Neutral Recording
The disclosure is recorded as a neutral chronological event.
The resulting record establishes that the disclosure was first observed within the declared implementation scope at a specific point in that implementation's chronological sequence.
NDI neither validates nor interprets the disclosure.
It records only the occurrence of the observation.
Stage 3 — Independent Reference
Once recorded, the chronological record becomes available as a neutral reference that downstream systems may use according to their own responsibilities.
NDI neither requires nor influences how that reference is subsequently used.
Stage 4 — Downstream Responsibilities
Following neutral recording, independent systems may perform responsibilities including:
Identity
Verification
Attribution
Provenance
Search
Ranking
Governance
Compliance
Artificial Intelligence
Audit
These responsibilities exist independently of NDI.
Their outputs remain distinct from the neutral chronological reference itself.
Relationship to Existing Architectures
NDI is intended to complement existing architectural responsibilities rather than replace them.
Existing technologies already address essential responsibilities throughout the digital ecosystem.
For example:
Identity systems answer who.
Verification systems establish whether something can be validated.
Provenance frameworks preserve the history of information after disclosure.
Governance frameworks apply policy and oversight.
Search systems optimise discovery.
Artificial intelligence performs interpretation, reasoning and action.
NDI proposes one additional architectural responsibility:
To establish a neutral chronological reference recording when a digital disclosure is first observed within a declared implementation scope before downstream systems begin their own responsibilities.
This proposal does not argue that existing architectures are incomplete.
It argues that this specific responsibility should be explicitly defined and kept separate from the responsibilities that follow it.
Relationship to ThopertyBox™
NDI originated during the development of the ThopertyBox™ vision.
This document, however, defines NDI as a standalone reference architecture rather than as a feature of any single platform, product or commercial ecosystem.
ThopertyBox represents one potential implementation that may choose to build upon the architecture.
This proposal does not prescribe the future ownership, stewardship, governance or commercial implementation of NDI.
Those questions remain separate from the architectural responsibility defined within this document.
Accordingly, this proposal should be evaluated on the basis of the architectural responsibility it defines rather than the commercial interests of any individual implementation.
Security Considerations
This document defines an architectural responsibility rather than a complete implementation.
This reference architecture intentionally separates architectural responsibility from implementation security. Security requirements are expected to be defined by individual implementations according to their deployment environment, operational requirements and threat model.
Accordingly, it does not specify implementation-specific security controls, threat models or operational safeguards.
Any implementation of NDI would be expected to address authentication, abuse prevention, replay protection, timestamp integrity, resilience, availability and other security considerations appropriate to its declared implementation scope.
These topics are recognised as essential implementation responsibilities and are expected to evolve alongside practical deployments and future technical guidance.
Invitation to Technical Review
NDI is presented as a public reference architecture for technical review and discussion.
Its purpose is not to declare a finished standard, but to define a clearly bounded architectural responsibility that can be independently examined, challenged and refined.
Constructive criticism is encouraged.
Questions regarding terminology, scope, interoperability, implementation, security and governance are both expected and welcomed.
Where improvements strengthen the clarity or robustness of the architecture while preserving its core responsibility, they should be considered part of the natural evolution of an open architectural proposal.
The architectural question posed by this document is intentionally simple:
Does the Internet and the AI ecosystem benefit from a neutral architectural responsibility that records when digital disclosures are first observed within a declared implementation scope, independently of all downstream evaluation and judgement?
If the answer is yes, the discussion naturally shifts from whether such a responsibility should exist to how it should be defined, implemented and governed.
Author
Steve Milazzo
Founder, ThopertyBox™
Status
Public Working Draft v2.1 (Review Candidate)
Repository
This document is maintained as an open architectural proposal and is expected to evolve through technical review, implementation experience and wider community discussion.




Version: 1.0
Status: Public Reference Architecture
Publication Date: 1 July 2026

PURPOSE

This document establishes the public reference architecture for the ThopertyBox™ framework.

It defines the architectural responsibilities of the framework, explains the separation between its principal components, and provides a public reference for technical discussion and constructive review.

This publication is intentionally presented as an architectural reference rather than a complete engineering specification or implementation guide.

Its purpose is to establish architectural principles upon which future technical documentation may be developed.

The objective is not to defend the architecture from criticism.

The objective is to strengthen it through open technical evaluation.

ARCHITECTURAL OBSERVATION

Modern AI infrastructure has advanced rapidly.

• Models have become more capable.
• Agents have become more autonomous.
• Governance continues to evolve.

Yet one architectural question remains comparatively underdeveloped:

How do we preserve confidence in what first entered an AI environment before downstream systems begin acting upon it?

This reference architecture explores that question.

ARCHITECTURAL PRINCIPLES

The framework separates architectural responsibilities rather than combining them.

NDI™ – Neutral Discovery Infrastructure

NDI™ provides a neutral record of first disclosure or first entry into participating environments.
Its responsibility is discovery.
It does not determine truth, ownership, governance or trust.

NCO™ – Neutral Chronological Orientation

NCO™ preserves the chronological relationship between recorded events.

Chronology is not truth.

It is an ordered reference from which later evaluation may begin.

TOI™ – Trusted Orientation Infrastructure

TOI™ applies contextual trust, governance and policy according to the needs of participating organisations while preserving the same neutral chronological reference.

SEPARATION OF RESPONSIBILITIES

The architecture intentionally separates:

• Discovery
• Chronology
• Trust
• Governance

Each responsibility can evolve independently while remaining complementary.

RELATIONSHIP TO EXISTING STANDARDS

ThopertyBox™ is not intended to replace existing standards.

Existing provenance, identity, integrity and governance frameworks continue to play essential roles.

The architectural hypothesis explored here is that an additional neutral reference point at the earliest stage of discovery may complement those systems rather than compete with them.

STEWARDSHIP PHILOSOPHY

ThopertyBox™ is not intended to become another dominant platform.

The long-term objective is stewardship through organisations capable of operating infrastructure responsibly at global scale.

The architecture is intended to support stewardship without requiring centralised control of the underlying architectural principles.

SCOPE OF THIS REFERENCE ARCHITECTURE

This publication establishes architectural principles only.

It does not define implementation methods, cryptographic mechanisms, deployment architectures, protocol specifications, performance characteristics or commercial arrangements.

These are intended for future technical documentation.

INVITATION TO TECHNICAL REVIEW

Constructive technical review is welcomed.

Engineering criticism is encouraged.

Architectural discussion is encouraged.

The objective is not to defend an idea from criticism.

The objective is to strengthen the architecture through it.

PUBLICATION RECORD

Reference Architecture v1.0 establishes the public architectural baseline from which subsequent Architecture Notes and technical documents may evolve.

VERSION HISTORY

Version 1.0 — Initial Public Reference Architecture.

© 2026 Steve Milazzo
Founder, ThopertyBox™

This document is intended as a public architectural reference rather than a complete technical specification. It establishes the separation of responsibilities and architectural principles of the framework. Detailed engineering specifications, protocol definitions and implementation guidance may be developed and published separately as the architecture evolves through constructive technical review.

