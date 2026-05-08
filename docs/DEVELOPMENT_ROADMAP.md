# Development Roadmap

## Method

Build thin vertical slices. Each slice must produce a visible, testable feature.

The portal must be developed incrementally as a purpose-built archival publication system rather than a generic CMS.

Every slice must:

- preserve prior functionality
- include verification steps
- avoid destructive schema changes unless explicitly planned
- maintain clear separation from the Archive OS preservation environment
- maintain privacy and consent protections
- produce a usable visible outcome

## Required verification after every slice

At minimum:

- npm install
- npm run lint
- npx tsc --noEmit
- npm run build
- route verification
- schema migration verification
- role/permission verification where applicable

## Phase A: Foundation

### Slice 0: Repository and documentation

- create repository
- add foundational docs
- add .env.example
- add baseline README
- add issue/PR workflow conventions

### Slice 1: Public shell

- Next.js scaffold
- homepage
- about page
- navigation
- footer
- responsive layout
- placeholder routes
- shared layout

### Slice 2: Database foundation

- Prisma initialization
- SQLite local development database
- migration discipline
- seed structure
- initial schema governance rules

### Slice 3: Authentication framework

- session framework
- login route
- logout route
- protected route middleware
- archivist login

### Slice 4: Authorization system

- role model
- permission middleware
- access guards
- public/admin boundaries
- protected admin routes

### Slice 5: Admin shell

- /admin dashboard
- admin navigation
- dashboard cards
- layout framework
- audit visibility placeholders

## Phase B: Publication and Editorial System

### Slice 6: Pages CMS

- create/edit/publish pages
- title, slug, body, status
- draft/published state
- revision timestamps

### Slice 7: Structured content blocks

- rich text blocks
- image embeds
- quote blocks
- timeline embeds
- citation blocks
- reusable layouts

### Slice 8: Publication system

- essays
- newsletters
- editorials
- publication issues
- scheduled publication
- publication indexes

### Slice 9: Contributor and authority records

- contributor model
- person records
- place records
- contributor pages
- editorial attribution

### Slice 10: Exhibit framework

- exhibits
- exhibit sections
- exhibit navigation
- exhibit landing pages
- exhibit metadata

### Slice 11: Timeline framework

- timeline entries
- chronological browsing
- linked people/places/events
- historical periods

## Phase C: Media and Access

### Slice 12: Media upload pipeline

- image upload
- media records
- upload validation
- MIME validation
- required metadata

### Slice 13: Derivative generation

- Sharp image processing
- thumbnail generation
- responsive derivatives
- storage abstraction
- derivative tracking

### Slice 14: Media metadata editor

- captions
- alt text
- rights statements
- related people
- related events
- visibility levels

### Slice 15: Access restriction enforcement

- visibility enforcement
- restricted media routing
- role-based media access
- download restrictions
- access logging

### Slice 16: Sensitive material handling

- explicit-content gating
- age affirmation
- suppressed thumbnails
- restricted indexing
- archivist approval workflow

## Phase D: Community and Governance

### Slice 17: Public submissions

- submission forms
- moderation queue
- contributor contact workflows
- consent acknowledgement

### Slice 18: Correction requests

- correction submission forms
- review queue
- editorial review workflow
- resolution states

### Slice 19: Takedown workflows

- takedown requests
- temporary suppression
- archivist review
- audit logging
- decision records

### Slice 20: Volunteer and community workflows

- volunteer resources
- onboarding pages
- community participation workflows
- contact forms

## Phase E: Discovery and Public UX

### Slice 21: Search and indexing

- site search
- search indexes
- filtering
- browse views
- metadata indexing

### Slice 22: Browse architecture

- browse by people
- browse by place
- browse by event
- browse by publication
- browse by exhibit

### Slice 23: SEO and metadata

- SEO metadata
- OpenGraph metadata
- structured metadata
- sitemap generation
- robots controls

### Slice 24: Accessibility review

- WCAG review
- keyboard navigation
- screen reader testing
- semantic markup review
- caption verification

## Phase F: Infrastructure and Operations

### Slice 25: S3-compatible storage integration

- Backblaze B2 integration
- object storage abstraction
- signed URLs where needed
- derivative storage

### Slice 26: Transactional email

- SMTP/SES integration
- notification templates
- moderation notifications
- password reset flows

### Slice 27: Privacy-preserving analytics

- Matomo integration
- consent-aware analytics
- dashboard metrics
- reporting views

### Slice 28: Audit infrastructure

- audit logs
- admin activity logs
- publication history
- moderation history
- access logs

### Slice 29: Integration monitoring

- integration status registry
- health checks
- failed job visibility
- queue visibility

### Slice 30: Containerization and deployment

- Docker setup
- environment management
- deployment scripts
- production configuration

### Slice 31: CI/CD

- GitHub Actions
- lint automation
- build verification
- migration verification
- deployment workflows

### Slice 32: PostgreSQL production migration

- PostgreSQL transition
- migration validation
- backup procedures
- restore verification

## Phase G: Archive OS Boundary Integration

### Slice 33: Archive OS import contract

- formal import boundaries
- approved derivative ingestion
- metadata ingestion rules
- identifier reconciliation
- validation rules

### Slice 34: Derivative synchronization

- derivative update workflows
- synchronization logging
- stale derivative detection
- synchronization visibility

### Slice 35: Restricted-content synchronization

- visibility synchronization
- restriction propagation
- suppression workflows
- access enforcement

### Slice 36: Provenance and reconciliation

- Archive OS identifiers
- provenance validation
- publication provenance visibility
- reconciliation reporting
