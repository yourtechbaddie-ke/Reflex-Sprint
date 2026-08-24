# Reflex 10-Minute Demo Script

## 0:00–1:15 — Problem
“Small retailers currently coordinate deliveries over WhatsApp and phone calls. The operational problem is not just messaging; it is the absence of a shared record of who owns a delivery, where it is in the process and what proves completion.”

## 1:15–3:00 — Retailer flow
Select **Retailer**. Create a delivery with customer, phone, address and item. Explain that the request receives a delivery ID and starts as `Open`.

## 3:00–5:15 — Dispatcher flow
Select **Dispatcher**. Show the board and open requests. Assign a rider. Explain that assignment is an explicit state transition, not a text message.

## 5:15–7:00 — Rider flow
Select **Rider**. Move an assigned delivery to `Picked Up`, then `Delivered`. Explain the allowed transition order and why invalid transitions should be rejected in production.

## 7:00–8:00 — Confirmation
Use the delivery ID in the confirmation field. Explain the camera/barcode path and manual fallback. Point out that a real production implementation would store proof metadata and the evidence itself separately.

## 8:00–9:00 — Architecture
Show `docs/architecture.md`. State that the prototype deliberately uses local persistence, while production uses authenticated roles, Firestore transactions, real-time listeners, offline persistence and audit events.

## 9:00–10:00 — Trade-offs and close
Show the trade-off log. Name the largest gap first: no live backend in the frozen build. Close with: “The value of Reflex is not another chat channel. It is one trustworthy delivery record with an accountable owner and visible status.”
