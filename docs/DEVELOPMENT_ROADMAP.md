# Development Roadmap

## Method

Build thin vertical slices. Each slice must produce a visible, testable feature.

The portal must be developed incrementally as a purpose-built archival publication system rather than a generic CMS.

Every slice must:

- preserve prior functionality
- include verification steps
- maintain clear separation from the Archive OS preservation environment
- maintain privacy and consent protections
- produce a usable visible outcome
- leave the application deployable

## Required Verification After Every Slice

At minimum:

- npm run lint
- npx tsc --noEmit
- npm run build

Additional verification may be required depending on the slice.

## Phase 1 — Barebones Public Site

The immediate objective is a deployable public website.

Implementation is governed by `docs/PHASE_1_SLICES.md`.

Target duration: 3–7 days of focused development.

## Phase 2 — Editorial CMS

- PostgreSQL
- Prisma
- Admin authentication
- Publications CRUD
- Media uploads
- Newsletter subscriber administration

## Phase 3 — Collections Portal

- Collection entities
- Search and browse
- Relationships
- Access restrictions

## Phase 4 — Public Programs and Community Interaction

- Events
- Volunteer applications
- Community submissions
- Correction and takedown requests

## Phase 5 — Institutional Integration and Preservation

- Archive OS synchronization
- Newsletter issue preservation
- Dashboards
- Automated exports
- Operational monitoring

## Governing Principle

No later phase may begin until the preceding phase is fully deployable and verified.
