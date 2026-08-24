# Reflex — Readiness Sprint

Reflex is a delivery-coordination MVP for small Kenyan retailers. It replaces WhatsApp/phone-based coordination with a simple workflow: **Retailer creates request → Dispatcher assigns rider → Rider updates status → Retailer sees progress and proof of delivery.**

## 🚀 Live MVP

**[Open the Reflex MVP](https://reflex-sprint-mvp.hatchable.site)**

The live prototype demonstrates the core delivery workflow, including request creation, rider assignment, status progression, delivery confirmation, filtering, and operational visibility.

This repository contains the frozen case-study build, architecture decisions, trade-off log, executive narrative, demo script, timing log, and defense preparation required by the Readiness Sprint assignment.

## Case study scope
- Retailer staff: customer name, phone, address, item description.
- Dispatcher: open requests and rider assignment.
- Rider: assigned deliveries and status updates: Assigned → Picked Up → Delivered.
- Order confirmation: browser camera/barcode scan when supported, with manual fallback.
- Real-time/sync behavior is represented in the MVP through a local event model; production synchronization is documented in `docs/architecture.md`.

## Repository map
- `index.html` — runnable single-page Reflex MVP.
- `styles.css` — responsive interface styling.
- `app.js` — request creation, assignment, status flow, filtering, persistence and scan fallback.
- `docs/architecture.md` — production architecture, data model and failure handling.
- `docs/trade-off-log.md` — five explicit trade-offs and acceptable-because decisions.
- `docs/executive-deck.md` — Problem → Solution → Architecture → Trade-offs → Roadmap narrative.
- `docs/demo-script.md` — 10-minute demo/presentation script.
- `docs/timing-log.md` — two dry-run timing records and revision notes.
- `docs/cross-examination.md` — State → Context → Evidence defense bank.
- `docs/requirements-traceability.md` — assignment requirement to repository evidence.

## Run locally
No build toolchain is required for the frozen MVP. Open `index.html` in a modern browser. For camera scanning, serve the folder from localhost/HTTPS because browser camera APIs are security-restricted.

## Design decision
The prototype intentionally uses vanilla HTML/CSS/JavaScript so the sprint artifact is immediately inspectable and dependency-light. The production target is a React/TypeScript client backed by Firebase Authentication, Firestore, Cloud Functions and Cloud Storage, with role-based access and offline-aware synchronization. That production choice is documented rather than pretending credentials/backend infrastructure exist in this assignment repository.

## Sprint deliverables
The assignment asks for a frozen build/design, executive deck, one-page trade-off log, demo script, timing evidence from at least two dry runs, and preparation for architecture, trade-off, edge-case and candor questions. Those artifacts are included here.

## Source of assignment requirements
See the uploaded **Reflex, The Readiness Sprint** brief. It defines the case study, five-day schedule, deliverables and scoring expectations.