ThopertyBox™ Reference Architecture v1.0

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

