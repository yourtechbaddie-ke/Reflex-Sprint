# Reflex Cross-Examination Bank

Use **State → Context → Evidence**. State the answer first. Explain why. Give a concrete detail. If the build cannot support an answer, say so.

## Why this stack?
**State:** I used a dependency-light prototype stack for the frozen build and a managed Firebase target for production.

**Context:** The sprint rewards a clear, defensible design; the brief does not mandate a stack.

**Evidence:** The prototype runs without a package install and the production architecture defines Auth, Firestore, Functions and Storage.

## Why not a custom API?
**State:** I would not add a custom backend before the operational workflow is validated.

**Context:** It adds infrastructure and failure modes without improving the sprint's core demonstration.

**Evidence:** The frozen build proves request, assignment and status transitions while `architecture.md` specifies the production boundary.

## What happens if two dispatchers assign one rider?
**State:** Production rejects the stale write through a transactional version check.

**Context:** Assignment is a state transition that must be atomic.

**Evidence:** The data model includes a `version` field and the architecture specifies expected-version transactions.

## What if the rider loses network?
**State:** The UI must show unsynced state and retry; it must not claim server success.

**Context:** Delivery work happens in environments with unreliable connectivity.

**Evidence:** Offline persistence and queued writes are explicitly part of the production architecture.

## What is your biggest weakness?
**State:** The frozen MVP is not a real multi-user backend.

**Context:** I deliberately optimized the sprint artifact for inspectability and a reliable demo.

**Evidence:** The prototype uses browser localStorage; the production design replaces it with Firestore synchronization and server-side authorization.

## Why not automate rider assignment?
**State:** I kept assignment dispatcher-controlled in the first version.

**Context:** A small retailer can validate the core workflow before introducing location and optimization complexity.

**Evidence:** Rider assignment is explicit and auditable in the prototype; automation is on the roadmap.

## What don't you know yet?
**State:** I do not yet have production evidence for dispatch optimization or notification delivery rates.

**Context:** Those are roadmap capabilities, not validated features of the frozen case-study build.

**Evidence:** I would measure assignment time, delivery completion time, notification success rate and conflict frequency in a pilot before optimizing.
