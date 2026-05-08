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

## Public launch thresholds

The portal has three distinct launch thresholds.

### Threshold 1: Basic live informational site

Target: end of Slice 5.

At this point the site must be hosted, live, publicly reachable, visually coherent, and editable by the archivist through a minimal CMS. It may function as a basic institutional website for the Sarasota LGBT Archive.

Allowed public functions:

- homepage
- about page
- mission statement
- project overview
- contact information or contact placeholder
- volunteer/contribute placeholder
- events/news placeholder
- basic public navigation
- protected admin shell
- minimal page-editing CMS for launch pages
- basic site design and theme
- deployment and operational documentation

Not yet allowed:

- public archival media publication
- donor submissions
- sensitive collection description
- sexually explicit material
- restricted community records
- collection search
- Archive OS synchronization
- preservation-master access of any kind

Required before this threshold is accepted:

- production deployment exists
- public URL works
- HTTPS works
- basic visual theme is implemented
- homepage and launch pages are editable through the CMS or a clearly documented content mechanism
- environment variables are documented
- admin routes are not publicly accessible
- placeholder public pages do not expose private data
- README includes deployment and local-development instructions
- repository contains a rollback note or redeployment procedure

Recommended cheapest initial hosting target:

- Vercel Hobby or Cloudflare Pages for the first public shell if no server-side persistence is needed yet
- if the Slice 5 CMS requires production persistence, use a low-cost managed PostgreSQL database or a small VPS with PostgreSQL
- defer S3 storage, Matomo, large media workflows, and Docker hardening until the application requires them

### Threshold 2: Public editorial and exhibit site

Target: end of Slice 10.

At this point the portal may support curated public writing, exhibits, contributor pages, and controlled editorial publication.

Allowed public functions:

- essays
- exhibit pages
- contributor pages
- curated non-sensitive media derivatives
- publication indexes
- public event/news pages

Still restricted:

- open public submissions
- sensitive media publication
- takedown-dependent workflows
- complex access-controlled archival browsing

### Threshold 3: Community archive portal

Target: end of Slice 19.

At this point the portal may begin operating as a community-facing archival platform with submission, correction, takedown, access-control, and moderation workflows.

Allowed public functions:

- moderated public submissions
- correction requests
- takedown requests
- access-controlled media
- explicit-material gating
- audit-backed moderation
- public archival media where rights and consent allow

## Phase A: Foundation and first public launch

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

### Slice 5: Basic live site, theme, minimal CMS, and admin shell

This is the first public launch threshold.

The site must be deployed and reachable on a public HTTPS URL by the end of this slice.

The site must also have a basic design system and a minimal CMS sufficient for the archivist to create and edit the first public pages without editing source code.

Public-facing requirements:

- live homepage
- live about page
- live project overview page
- live contribute/volunteer placeholder page
- live events/news placeholder page
- basic navigation
- footer with contact or forthcoming-contact language
- no archival media publication yet
- no public submissions yet
- no restricted collection data yet

Basic design and theme requirements:

- site name and identity treatment
- readable typographic scale
- consistent page layout
- responsive mobile-first design
- accessible color contrast
- header and footer design
- button/link styles
- basic card styles
- announcement/banner component
- simple homepage sections
- design tokens for color, spacing, borders, and typography
- theme documented in a design/theme specification

Minimal CMS requirements:

- admin page list
- create page
- edit page
- publish/unpublish page
- title field
- slug field
- summary field
- body field using plain Markdown or a simple rich-text field
- status field: draft or published
- navigation visibility flag
- homepage content editable through the CMS or through a clearly documented special page record
- seeded initial pages for homepage, about, project overview, contribute/volunteer, and events/news

Admin requirements:

- /admin dashboard
- admin navigation
- dashboard cards
- layout framework
- audit visibility placeholders
- admin route protection
- visible sign-in/sign-out behavior
- link from admin dashboard to page management

Deployment requirements:

- choose initial hosting target
- configure deployment from GitHub
- configure public URL
- configure HTTPS
- document required environment variables
- document deployment process
- document rollback or redeploy process
- verify that public pages load in production
- verify that /admin is protected in production
- verify that CMS-edited public pages render correctly in production

Suggested first-launch hosting model:

- if the CMS is database-backed in production, use a low-cost managed PostgreSQL provider or small VPS rather than non-persistent SQLite
- if Vercel or Cloudflare Pages is used for the first launch, pair it with a managed production database when editable content must persist
- use SQLite only for local prototype work unless persistence limitations are explicitly accepted and documented
- defer S3 media storage until media publication begins

Do not implement at Slice 5:

- S3 media storage
- public uploads
- archival object publication
- donor records
- Archive OS import
- Matomo analytics unless trivial and privacy-reviewed
- transactional email unless needed for login

## Phase B: Publication and Editorial System

### Slice 6: Pages CMS expansion

- expand the Slice 5 minimal CMS
- add revision history
- add editorial notes
- add draft preview
- add scheduled publication preparation
- improve validation

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
