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
- schema migration verification where applicable
- role/permission verification where applicable

## Public launch thresholds

The portal has three distinct launch thresholds.

### Threshold 1: Basic live informational site

Target: end of Slice 5.

At this point the site must be hosted, live, publicly reachable, visually coherent, editable through a file-based content workflow, and able to receive basic public contact messages. It may function as a basic institutional website for the Sarasota LGBT Archive.

Allowed public functions:

- homepage
- about page
- mission statement
- project overview
- contact page
- contact form
- volunteer and contribute pages
- oral history participation invitation
- donor and funding invitation
- events and news placeholder
- basic public navigation
- protected admin shell
- file-based content management for launch pages
- basic site design and theme
- deployment and operational documentation

Not yet allowed:

- public archival media publication
- donor submissions with uploads
- sensitive collection description
- sexually explicit material
- restricted community records
- collection search
- Archive OS synchronization
- preservation-master access of any kind
- file attachments through the contact form

Required before this threshold is accepted:

- production deployment exists
- public URL works
- HTTPS works
- custom domain may be configured
- basic visual theme is implemented
- launch pages are editable locally and deploy correctly from GitHub
- contact form works in production or has a documented safe temporary fallback
- contact form does not accept file uploads
- contact form includes basic spam protection
- Google Workspace email delivery is configured or documented
- environment variables are documented
- admin routes are not publicly accessible
- placeholder public pages do not expose private data
- README includes deployment and local-development instructions
- repository contains a rollback note or redeployment procedure

Recommended low-cost initial hosting target:

- Vercel Hobby or Cloudflare Pages
- Google Workspace for institutional email
- purchased custom domain
- Cloudflare DNS and SSL if desired

### Threshold 2: Public editorial and exhibit site

Target: end of Slice 10.

At this point the portal may support curated public writing, exhibits, contributor pages, and controlled editorial publication.

### Threshold 3: Community archive portal

Target: end of Slice 19.

At this point the portal may begin operating as a community-facing archival platform with submission, correction, takedown, access-control, and moderation workflows.

## Phase A: Foundation and first public launch

### Slice 0: Repository and documentation

- create repository
- add foundational docs
- add .env.example
- add baseline README
- add issue and PR workflow conventions

### Slice 1: Public shell

- Next.js scaffold
- homepage
- about page
- navigation
- footer
- responsive layout
- placeholder routes
- shared layout

### Slice 2: Optional database foundation

Database infrastructure is optional for Slice 5.

If a static-first content model is used, production page content does not require a database.

Possible uses at this stage:

- future authentication persistence
- future contact-message storage
- prototype schema work

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
- public and admin boundaries
- protected admin routes

### Slice 5: Basic live site, theme, file-based content workflow, contact form, and admin shell

This is the first public launch threshold.

The site must be deployed and reachable on a public HTTPS URL.

Content is edited locally in Markdown, MDX, JSON, or equivalent files and published through Git-based deployment.

A browser-based database-backed CMS is explicitly deferred until later slices.

Public-facing requirements include:

- homepage
- about page
- project overview page
- contact page and form
- volunteer and contribute page
- donor and funding invitation
- oral history participation invitation
- events and news placeholder page

Administrative requirements include:

- login and logout
- protected /admin area
- deployment documentation
- environment-variable documentation
- rollback and redeploy documentation

Design requirements include:

- SVG header logo
- responsive navigation
- accessible typography and contrast
- mobile-first layout
- form styles
- homepage sections

Do not implement at Slice 5:

- database-backed editorial CMS
- archival uploads
- media publication workflows
- public search
- exhibits
- timelines
- S3 storage
- Archive OS synchronization
- full analytics stack

## Phase B: Publication and Editorial System

### Slice 6: Database-backed CMS expansion

- browser-based page management
- create and edit pages in admin
- revision history
- editorial notes
- draft preview
- scheduled publication preparation
- validation improvements

### Slice 7: Structured content blocks

### Slice 8: Publication system

### Slice 9: Contributor and authority records

### Slice 10: Exhibit framework

### Slice 11: Timeline framework

## Phase C: Media and Access

### Slice 12: Media upload pipeline

### Slice 13: Derivative generation

### Slice 14: Media metadata editor

### Slice 15: Access restriction enforcement

### Slice 16: Sensitive material handling

## Phase D: Community and Governance

### Slice 17: Public submissions

### Slice 18: Correction requests

### Slice 19: Takedown workflows

### Slice 20: Volunteer and community workflows

## Phase E: Discovery and Public UX

### Slice 21: Search and indexing

### Slice 22: Browse architecture

### Slice 23: SEO and metadata

### Slice 24: Accessibility review

## Phase F: Infrastructure and Operations

### Slice 25: S3-compatible storage integration

### Slice 26: Transactional email

### Slice 27: Privacy-preserving analytics

### Slice 28: Audit infrastructure

### Slice 29: Integration monitoring

### Slice 30: Containerization and deployment

### Slice 31: CI/CD

### Slice 32: PostgreSQL production migration

## Phase G: Archive OS Boundary Integration

### Slice 33: Archive OS import contract

### Slice 34: Derivative synchronization

### Slice 35: Restricted-content synchronization

### Slice 36: Provenance and reconciliation
