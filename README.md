# Reflex — Readiness Sprint

Reflex is a delivery-coordination MVP for small Kenyan retailers. It replaces WhatsApp/phone-based coordination with a simple workflow: **Retailer creates request → Dispatcher assigns rider → Rider updates status → Retailer sees progress and proof of delivery.**

## 🚀 Live Prototype Links

### Reflex Control Room — Frontend / UX
**https://reflex-control-room.hatchable.site/**

The Control Room is the dedicated frontend/UX prototype for the sprint. It demonstrates the operational dashboard, delivery metrics, request creation, search/filtering, rider assignment, status progression and delivery-code confirmation flow.

### Reflex MVP
**https://reflex-sprint-mvp.hatchable.site**

The original frozen MVP remains available as the team's broader sprint artifact.

## Frontend / UX

The dedicated frontend implementation is in `Frontend/`:

- `Frontend/index.html` — semantic Control Room interface structure.
- `Frontend/styles.css` — responsive visual system and interaction states.
- `Frontend/app.js` — frontend interactions and browser-local prototype state.
- `Frontend/README.md` — frontend scope, local run instructions and ownership boundary.
- `docs/frontend-ux.md` — UX principles, interface areas, accessibility notes and frozen-MVP vs production boundary.

The frontend is intentionally separated from backend responsibilities. The frozen Control Room uses browser `localStorage` for demo persistence; it does **not** claim to provide production multi-user synchronization, secure persistence or server-side authorization.

## Case study scope
- Retailer staff: customer name, phone, address, item description.
- Dispatcher: open requests and rider assignment.
- Rider: assigned deliveries and status updates: Assigned → Picked Up → Delivered.
- Order confirmation: browser camera/barcode scan when supported, with manual fallback.
- Real-time/sync behavior is represented in the frozen prototype; production synchronization is documented in `docs/architecture.md`.

## Repository map
- `index.html` / `styles.css` / `app.js` — original frozen single-page MVP.
- `Frontend/` — dedicated Reflex Control Room frontend/UX implementation.
- `docs/architecture.md` — production architecture, data model and failure handling.
- `docs/frontend-ux.md` — frontend UX decisions and ownership boundary.
- `docs/trade-off-log.md` — explicit trade-offs and acceptable-because decisions.
- `docs/executive-deck.md` — Problem → Solution → Architecture → Trade-offs → Roadmap narrative.
- `docs/demo-script.md` — 10-minute demo/presentation script.
- `docs/timing-log.md` — dry-run timing evidence and revision notes.
- `docs/cross-examination.md` — State → Context → Evidence defense bank.
- `docs/requirements-traceability.md` — assignment requirement to repository evidence.

## Run locally
For the original frozen MVP, open `index.html` in a modern browser. For the dedicated Control Room, open `Frontend/index.html`. No frontend build toolchain is required for either frozen prototype.

## Design decision
The frozen sprint artifacts intentionally use dependency-light HTML/CSS/JavaScript so the work remains immediately inspectable. The production target is a React/TypeScript client backed by Firebase Authentication, Firestore, Cloud Functions and Cloud Storage, with role-based access and offline-aware synchronization. Production architecture is documented rather than pretending credentials/backend infrastructure exist in this assignment repository.

## Sprint deliverables
The repository contains the frozen build/design, executive narrative, trade-off log, demo script, timing evidence, requirements traceability, cross-examination preparation and the dedicated Frontend/UX Control Room.

## Source of assignment requirements
See the uploaded **Reflex, The Readiness Sprint** brief. It defines the case study, five-day schedule, deliverables and scoring expectations.