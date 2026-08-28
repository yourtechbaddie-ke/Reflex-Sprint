# Reflex — Frontend & UX Design Notes

## Purpose

The Reflex Control Room is the frontend expression of the core delivery workflow: **request → assignment → status progression → confirmation**.

## UX principles

1. **Scan before drill-down.** Operational metrics appear before individual delivery records.
2. **Make ownership visible.** Assigned riders are shown directly on delivery cards.
3. **Make status actionable.** The primary action changes with the delivery state.
4. **Keep the workflow short.** A user should not need to navigate through multiple screens to progress a delivery.
5. **Design for failure.** Confirmation includes a manual delivery-code fallback and the UI avoids implying a backend sync that does not exist in the frozen build.
6. **Responsive by default.** Cards and metric grids collapse for smaller screens while preserving the same workflow.

## Main interface areas

### 1. Header
Provides persistent product identity and a role-view selector for the prototype.

### 2. Hero / operational promise
Communicates the central product idea: every delivery has an owner, status and trail. A small sync indicator clarifies that the frozen build is browser-local.

### 3. Retailer request form
Captures the minimum delivery information needed for the case study: customer, phone, address and item.

### 4. Metrics
Shows Open, Assigned, Picked Up and Delivered counts. These are derived from the same frontend delivery records shown in the board.

### 5. Delivery board
Provides search, status filters and state-specific actions. This is the main control-room surface.

### 6. Rider confirmation
Provides delivery-code confirmation as a resilient fallback. A future production version can add camera scanning without removing the manual path.

## Accessibility considerations

- Semantic labels are used for inputs and controls.
- Focus states are visible.
- `aria-live` is used for sync and confirmation feedback.
- Buttons have explicit action labels.
- Layout remains usable at narrow viewport widths.

## Frozen MVP vs production

The frontend prototype persists demo state in `localStorage`. It does not claim to provide multi-user synchronization, secure persistence or server-side authorization. Those responsibilities belong to the production backend architecture and should be integrated through the team's agreed contract.

## Frontend ownership boundary

The frontend/UX contribution includes interface structure, styling, responsive behaviour, user interaction and presentation of delivery state. Backend services, database operations, authentication and server-side authorization are separate responsibilities and should not be represented as frontend work.