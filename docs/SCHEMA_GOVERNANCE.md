# Schema Governance

## Purpose

This document defines how database schema changes must be handled for the Sarasota LGBT Archive Public Portal.

The portal is a public access, publication, exhibit, communication, and community-facing system. It is not the Archive OS preservation repository. Schema design must therefore protect privacy, preserve publication history, and maintain a clear boundary between public portal data and preservation-authority data.

## Core principles

- Prefer additive migrations.
- Avoid destructive migrations unless explicitly approved.
- Preserve publication and moderation history.
- Preserve auditability for administrative actions.
- Do not store preservation masters, donor agreements, forensic disk images, full PREMIS event logs, or private archival deposits.
- Keep Archive OS identifiers as references, not as evidence that the portal is the preservation authority.
- Treat sensitive visibility and consent fields as first-class data, not optional notes.

## Required fields for persistent models

Most persistent models should include:

- id
- createdAt
- updatedAt
- createdById where applicable
- updatedById where applicable
- status where applicable
- visibilityLevel where applicable

Public content models should additionally include:

- slug
- title
- summary
- body or structured content
- publishedAt
- reviewedById where applicable
- rightsStatement where applicable
- citationText where applicable
- seoTitle where applicable
- seoDescription where applicable
- searchIndexingAllowed

## Identifier policy

All primary records must use application-controlled stable identifiers.

Do not use filenames, call numbers, display titles, or external provider IDs as primary identifiers.

Archive OS identifiers may be stored as external references for reconciliation, provenance display, and synchronization, but they must not replace portal primary keys.

## Slug policy

Public slugs must be unique within their routing scope.

Examples:

- page slugs must be unique among pages
- exhibit slugs must be unique among exhibits
- publication slugs must be unique among publications
- contributor slugs must be unique among contributors

Slug changes must not silently break public URLs once content has been published. Later slices should support redirect records or historical slug tracking.

## Migration policy

Allowed by default:

- adding new tables
- adding nullable fields
- adding indexes
- adding new enum values where backward compatible
- adding join tables
- adding audit tables

Requires explicit review:

- deleting tables
- deleting columns
- renaming columns
- changing enum values already used by records
- changing required fields on existing populated tables
- changing relationship cardinality
- changing visibility or permission semantics
- changing identifiers or slug behavior

## Development and production database policy

SQLite may be used for local development and early prototyping.

Production CMS content, contact messages, user sessions, and admin data must use persistent production storage. If the site is hosted on Vercel, Cloudflare Pages, or another stateless platform, a managed PostgreSQL database or equivalent persistent database must be used once editable production content is required.

Do not treat a local SQLite database as a production content store.

## Seed data policy

Seed data may be used for:

- initial launch pages
- test users
- role definitions
- permission definitions
- sample dashboard cards
- placeholder public pages

Seed data must not include real restricted donor data, private archival deposits, confidential contact messages, or sensitive community records.

## Deletion policy

Hard deletion should be avoided for public content, submitted messages, takedown requests, correction requests, and administrative actions.

Prefer status changes such as:

- archived
- withdrawn
- suppressed
- spam
- resolved
- closed

Hard deletion may be used for development-only test data before production launch.

## Audit expectations

The following actions should eventually produce audit records:

- user login where security-relevant
- failed admin access where practical
- page creation
- page publication
- page withdrawal
- page deletion or suppression
- contact message review
- correction request review
- takedown request review
- media publication
- media restriction changes
- role changes
- integration configuration changes

Slice 5 may use placeholders for audit visibility, but the schema must not prevent later audit logging.

## Privacy fields

Models that may expose people, identity, images, public submissions, contact messages, or community-sensitive material should support privacy and review fields appropriate to their risk.

Relevant fields may include:

- visibilityLevel
- consentStatus
- sensitivityLevel
- containsIdentifiablePeople
- searchIndexingAllowed
- minimumRoleRequired
- reviewedById
- reviewedAt
- withdrawnAt
- suppressionReason

## Relationship policy

Relationships should be explicit and queryable.

Avoid encoding major relationships only in body text.

Examples of relationships requiring structured support in later slices:

- media to people
- media to places
- media to events
- media to exhibits
- publications to contributors
- exhibits to sections
- pages to navigation
- contact messages to review status
- takedown requests to affected records

## Rollback expectations

Every slice that changes schema must document:

- migration command used
- tables changed
- fields added or changed
- seed changes
- rollback or restore expectation
- known data risks

At minimum, development verification must include:

- npx prisma validate
- npx prisma migrate dev where applicable
- npm run build
- npm run lint
- npx tsc --noEmit
