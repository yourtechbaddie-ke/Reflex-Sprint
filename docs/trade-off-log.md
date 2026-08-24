# Reflex Trade-off Log

| Weak point | Acceptable because… | With more time… |
|---|---|---|
| The frozen MVP uses localStorage rather than a live backend. | The sprint prioritizes a defensible workflow and a runnable artifact without credentials or deployment dependencies. | Connect the same UI to Firestore with authentication, transactions and offline persistence. |
| Rider assignment is a simple manual selection. | Small retailers can start with a dispatcher-controlled workflow; automatic dispatch is not required to prove the core value. | Add availability, location, workload and SLA-aware assignment rules. |
| The prototype's scan confirmation has a manual fallback and does not implement a full barcode service. | Camera availability varies by browser/device, and the assignment asks for a defensible system rather than a production scanning stack. | Use QR/barcode generation, device camera scanning and server-side code validation. |
| Address handling is plain text. | It is enough to demonstrate the request and assignment workflow. | Add normalized locations, map/geocoding support and delivery-zone validation. |
| Notifications are not implemented in the frozen build. | Status visibility inside one shared record proves the core problem is being solved first. | Add WhatsApp/SMS/push notifications with delivery receipts and retry handling. |

## What I would not hide
The largest gap is real-time multi-user persistence. I would not describe localStorage as production-ready synchronization. The prototype proves the interaction model; the production architecture specifies how synchronization, authorization, conflict handling and auditability would work.