# Reflex Control Room — Frontend / UX

This folder contains the dedicated Reflex Control Room frontend prototype.

## Live prototype

**https://reflex-control-room.hatchable.site/**

## Frontend scope

The Control Room focuses on the user experience for delivery coordination:

- Retailer delivery request creation
- Operational delivery metrics
- Delivery search and status filters
- Dispatcher rider assignment
- Rider status progression
- Delivery confirmation using a delivery code fallback
- Responsive desktop, tablet and mobile layout
- Clear sync/persistence feedback
- Empty and feedback states

## Files

- `index.html` — semantic interface structure and workflow controls.
- `styles.css` — responsive visual system, layout, states and accessibility-focused focus treatment.
- `app.js` — frontend interactions, prototype state, filtering, request creation, assignment and status progression.

## Data boundary

The frozen frontend uses browser `localStorage` for demo persistence. This is intentionally **not** presented as production multi-user storage. Production authentication, database persistence, server-side authorization, real-time synchronization and backend services remain outside this frontend folder and should be integrated through the team's agreed API/backend contract.

## Presentation ownership

The frontend/UX contribution covers interface structure, visual hierarchy, responsive behaviour and interaction patterns. Backend/database/authentication implementation should be attributed to the relevant team members.

## Local run

Open `index.html` in a modern browser. No frontend build toolchain is required for the frozen prototype.