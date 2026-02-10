=========================================================
CAIA Mental Models
Non-Normative Draft
=========================================================

STATUS
------
This document describes conceptual models intended to help implementers
reason about CAIA systems consistently.

These models are explanatory, not prescriptive.

---------------------------------------------------------
1. PURPOSE
---------------------------------------------------------

The purpose of this document is to provide shared mental models that
reduce mismatched assumptions between implementations.

---------------------------------------------------------
2. CAIA AS A COMPOSITIONAL SYSTEM
---------------------------------------------------------

CAIA assumes systems are composed of interoperable modules that may be:
- Physically distributed
- Independently developed
- Dynamically combined

No assumption is made about deployment topology.

---------------------------------------------------------
3. ROLE SEPARATION
---------------------------------------------------------

CAIA distinguishes between logical roles rather than concrete devices.

A single physical device may embody multiple roles, and a single role
may span multiple physical components.

---------------------------------------------------------
4. CONTROL VS DATA
---------------------------------------------------------

CAIA treats control coordination and data exchange as distinct concerns,
even when they share transport mechanisms.

Implementations should avoid conflating the two conceptually.

---------------------------------------------------------
5. NON-GOALS
---------------------------------------------------------

This document does not attempt to:
- Define architectures
- Define APIs
- Recommend implementation strategies

---------------------------------------------------------
END OF DOCUMENT
=========================================================
