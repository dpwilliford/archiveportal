# Sarasota LGBT Archive Public Portal

## Purpose

This repository defines and implements the public-facing web portal for the Sarasota LGBT Archive.

The portal is the archive's publication, access, engagement, event, exhibit, and community-submission platform. It is not the long-term preservation repository and is not the system of record for preservation masters, donor records, chain-of-custody documentation, preservation events, or restricted personally identifying information.

The first objective is not to build the full institutional platform. The first objective is to launch a functioning, public, barebones site quickly, while preserving the architectural boundaries needed for later growth.

## Source-of-Truth Boundary

The Archive OS is the preservation authority. It stores preservation masters, donor files, restricted records, PREMIS events, fixity logs, rights records, and chain-of-custody documentation.

The public portal may store and serve only:

- public-facing pages
- curated interpretation
- publication content
- exhibit content
- timeline entries
- public derivatives of media
- newsletter/contact submissions
- approved public metadata
- dashboard metrics derived from public or administrative portal data

The public portal must not store preservation masters, donor PII, private donor agreements, full chain-of-custody records, forensic ingest data, or archival system-of-record metadata.

## Immediate MVP

The first live version must be deliberately small.

Required public pages:

- Home
- About
- Mission
- Timeline
- Publications
- Oral Histories placeholder
- Get Involved
- Donate
- Contact
- Privacy Policy

Required technical behavior:

- responsive layout
- accessible semantic HTML
- fast static or mostly-static rendering
- contact form with spam protection or temporary mailto fallback
- newsletter signup with local consent tracking and double opt-in
- basic SEO and social preview metadata
- deployment-ready configuration
- clear local development instructions

Explicitly out of scope for the first live version:

- donor accounts
- board dashboards
- public user accounts
- collection search
- item-level archival records
- IIIF
- oral history media synchronization
- automated import from Archive OS
- public submission upload workflows
- complex CMS permissions
- preservation storage workflows

## Development Method

This project must be developed as thin vertical slices. Each slice must produce a visible, testable feature. Do not build a generic CMS. Build a custom archival publication portal for this specific institution.

Claude Code must preserve the following rule: every phase should leave the site deployable.

## Initial Stack

Recommended baseline:

- Next.js
- TypeScript
- Tailwind CSS
- Prisma only when persistence is introduced
- SQLite for local prototype persistence
- PostgreSQL for production persistence
- Backblaze B2 or another S3-compatible service for web derivatives, not preservation masters
- Sharp for derivative generation when image processing is introduced
- Auth.js or custom session authentication only when admin editing is introduced
- Matomo or Cloudflare Web Analytics for privacy-respecting analytics
- SMTP-compatible transactional email when forms are introduced
- GitHub Actions for CI
- Cloudflare for DNS, SSL, caching, and possibly hosting
- Listmonk for self-hosted newsletter publishing (deployed after launch)
- Amazon SES for confirmation and newsletter email delivery

## Documentation Index

Read these documents before generating or modifying code:

- `docs/MVP_SCOPE.md`
- `docs/SYSTEM_ARCHITECTURE.md`
- `docs/DEVELOPMENT_ROADMAP.md`
- `docs/SERVICE_INVENTORY.md`
- `docs/NEWSLETTER_ARCHITECTURE.md`
- `CLAUDE.md`

## Build Discipline

Before adding a database, authentication, uploads, dashboards, or CMS editing, Claude Code must first complete the barebones public site. The site should be useful even if it is only static content at launch.
