CAIA Reference Architecture — Illustrative Usage Narrative
Version: 0.9
Status: Non-Normative (Frozen)
Applies to: CAIA Specification Version 0.9

---------------------------------------------------------
FREEZE NOTE
---------------------------------------------------------

This document is frozen with respect to CAIA Specification Version 0.9.

No changes to structure, narrative stages, or referenced semantics are
intended without a corresponding version increment of this document.
Editorial corrections that reduce ambiguity may be made without
altering versioned intent.

---------------------------------------------------------
1. PURPOSE
---------------------------------------------------------

This document presents an illustrative reference architecture and usage
narrative designed to exercise the full range of system semantics defined
by the CAIA specification.

It is intended to support understanding, review, and discussion of the
specification by implementers, reviewers, and stakeholders.

This document is non-normative. The CAIA specification is authoritative.
Nothing herein defines requirements, compliance criteria, or preferred
implementations.

---------------------------------------------------------
2. SCOPE AND INTENT
---------------------------------------------------------

The reference architecture and stages described herein:

- Demonstrate system growth through addition rather than replacement
- Illustrate composability across heterogeneous modules
- Exercise capture, routing, timing, monitoring, and fault semantics
- Avoid mandating transports, operating systems, physical form factors,
  or business models

The examples are illustrative, not exhaustive. Valid CAIA systems may be
strict subsets or supersets of those described.

---------------------------------------------------------
3. ILLUSTRATIVE SYSTEM COMPONENTS
---------------------------------------------------------
(References correspond to CAIA Specification Version 0.9)

The narrative assumes the existence of the following categories of
components, without constraining their physical realization.

3.1 Coordinator (§2.1, §3.2, §5.1)

A coordinating element that provides:
- Module enumeration and identity management (§2.1)
- Clocking and timing authority (§3.2)
- Routing and configuration authority (§3.3)
- System-level fault aggregation (§5.1)
- Host (e.g., DAW) interface (§3.6)

The coordinator performs no audio capture or generation.

3.2 Simple I/O Unit (§3.1)

A small edge device that provides:
- One audio input (e.g., instrument or microphone)
- One audio output intended for monitoring

This represents the smallest practical capture-and-monitoring unit used
in the narrative.

3.3 Composite Devices (§4.1–§4.3)

Composite devices are single physical units that enumerate as multiple
logical modules (§4.1), each with independent identity (§2.3), routing,
and fault semantics, while sharing enclosure and backhaul.

---------------------------------------------------------
4. USAGE NARRATIVE
---------------------------------------------------------

The following stages describe a progressive, real-world usage story.
Each stage builds on the previous one without invalidating it.

---------------------------------------------------------
Stage 1: Solo Musician
---------------------------------------------------------

A musician connects a simple I/O unit to the system and records a guitar.
The system enumerates the device, exposes a stable logical input, and
provides monitoring through the same unit.

The system is complete and functional at this minimal scale.

---------------------------------------------------------
Stage 2: Collaborator
---------------------------------------------------------

A second musician arrives with a bass and their own simple I/O unit.
The new device is added to the system without reconfiguration or
replacement of existing components.

Both musicians record simultaneously, each with independent capture and
monitoring, operating within a shared timing domain.

---------------------------------------------------------
Stage 3: Band with Composite Devices
---------------------------------------------------------

As the group expands into a full band, composite devices are introduced
to support additional instruments, microphones, and a drum kit.

These composite devices enumerate multiple logical inputs (and, where
appropriate, monitoring outputs) while maintaining internal timing
alignment.

Simple I/O units and composite devices coexist within the same system.

---------------------------------------------------------
Stage 4: Band with Sound Engineer
---------------------------------------------------------

An engineer joins the session and connects an output-only monitoring
device for control-room listening.

This device consumes system outputs without participating in capture
and without interfering with performer monitoring or routing.

---------------------------------------------------------
Stage 5: Incremental Instrument Addition
---------------------------------------------------------

The drummer decides to add a cowbell and connects a very small, single-
input device dedicated to that instrument.

The new input is added without altering existing routing, identities,
or timing relationships, demonstrating fine-grained system expansion.

---------------------------------------------------------
5. SPEC CONCEPTS EXERCISED (DESCRIPTIVE)
---------------------------------------------------------
(References correspond to CAIA Specification Version 0.9)

The stages above collectively exercise the following specification
concepts:

- Module enumeration and discovery (§2.1)
- Logical channel abstraction (§2.3)
- Stable identity under system growth (§2.5)
- Independent capture sources (§3.1)
- Shared timing and clocking domains (§3.2)
- Composite module declaration (§4.1–§4.3)
- Mixed-granularity systems (§4.2)
- Output-only participation (§3.4)
- Role differentiation without hierarchy (§3.5)
- Incremental, late-bound expansion (§2.4)

This mapping is descriptive and non-exhaustive.
