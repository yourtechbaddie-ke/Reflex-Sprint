# Reflex Executive Deck

## Slide 1 — Problem
**Takeaway:** Delivery coordination is fragmented, so retailers lose visibility and proof.

Small Kenyan retailers coordinate deliveries through WhatsApp and phone calls. There is no reliable record of assignment, status or proof of delivery.

## Slide 2 — Solution
**Takeaway:** Reflex turns a fragmented conversation into one shared delivery record.

Retailer creates → dispatcher assigns → rider updates → retailer sees the current state.

## Slide 3 — Architecture
**Takeaway:** The architecture protects the delivery record as the source of truth.

Frozen MVP: vanilla HTML/CSS/JS + local persistence. Production target: React/TypeScript + Firebase Auth + Firestore + Functions + Storage. Role-based access and transactional status changes protect state integrity.

## Slide 4 — Trade-offs
**Takeaway:** I deliberately traded production depth for sprint-speed demonstrability.

Local persistence, manual assignment, limited scan implementation, plain-text addresses and no notifications are known gaps—not hidden failures.

## Slide 5 — Edge cases
**Takeaway:** The next version must make failure visible rather than silently losing state.

Network loss → retry/unsynced state. Concurrent assignment → transaction/version check. Invalid status transition → server rejection. Camera unavailable → manual code fallback.

## Slide 6 — Roadmap
**Takeaway:** The roadmap follows operational risk, not feature volume.

1. Live multi-user backend and authentication.
2. Reliable offline sync and conflict handling.
3. Proof-of-delivery capture and verification.
4. Notifications and delivery SLAs.
5. Dispatch optimization and reporting.

## Closing
**Takeaway:** Reflex is valuable because it gives a retailer one trustworthy answer to a simple question: “Where is my delivery?”
