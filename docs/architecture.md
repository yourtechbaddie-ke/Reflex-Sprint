# Reflex Architecture

## 1. Decision
For the frozen sprint prototype, Reflex uses vanilla HTML/CSS/JavaScript and browser localStorage. This keeps the artifact dependency-light and immediately demoable. For production, the recommended architecture is React + TypeScript, Firebase Authentication, Firestore, Cloud Functions and Cloud Storage.

## 2. Core flow
1. Retailer creates a delivery request.
2. Request is stored with an immutable delivery ID and `Open` status.
3. Dispatcher views open requests and assigns an available rider.
4. Assignment changes status to `Assigned` and records the rider.
5. Rider changes status to `Picked Up`, then `Delivered`.
6. Delivery confirmation records proof metadata; barcode/QR scanning can resolve the delivery ID.
7. Retailer consumes the same delivery record rather than relying on a separate phone/WhatsApp update.

## 3. Production components
- **Client:** React/TypeScript responsive web app.
- **Auth:** Firebase Authentication with role claims: retailer, dispatcher, rider.
- **Database:** Firestore collections for deliveries, users, retailers and status events.
- **Server rules:** Firestore security rules enforce role and ownership constraints.
- **Functions:** validate transitions, write audit events, send notifications and process proof-of-delivery metadata.
- **Storage:** Cloud Storage for signed proof-of-delivery images/documents.
- **Sync:** Firestore listeners provide real-time updates; offline persistence queues writes until connectivity returns.

## 4. Data model
`deliveries/{deliveryId}`
- `retailerId`
- `customerName`
- `customerPhone`
- `address`
- `itemDescription`
- `riderId`
- `status`
- `createdAt`
- `assignedAt`
- `pickedUpAt`
- `deliveredAt`
- `proofOfDeliveryId`
- `version`

`deliveries/{deliveryId}/events/{eventId}`
- `type`
- `actorId`
- `fromStatus`
- `toStatus`
- `createdAt`
- `deviceId`

`users/{userId}`
- `role`
- `displayName`
- `retailerId`
- `active`

## 5. Status integrity
Allowed transitions are `Open → Assigned → Picked Up → Delivered`. A server-side transaction validates the current status before accepting a transition. If two clients race to update the same delivery, only the transaction that sees the expected current version succeeds; the other receives a conflict and refreshes.

## 6. Failure cases
- **Network loss:** local queue/retry; UI shows unsynced state instead of claiming success.
- **Duplicate request:** client-generated idempotency key plus server validation.
- **Two dispatchers assign simultaneously:** transactional update with expected version.
- **Rider attempts invalid transition:** reject at server rules/function layer.
- **Proof upload fails:** delivery remains `Picked Up` until proof requirements are satisfied, depending on the retailer's policy.
- **Camera unavailable:** manual delivery-code entry remains available.

## 7. Why not a custom backend now?
A custom API/database would create more infrastructure and failure modes than the sprint needs. The prototype demonstrates the workflow and decision logic while keeping the production architecture explicit enough to defend.
