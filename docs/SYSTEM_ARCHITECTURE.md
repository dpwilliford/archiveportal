# System Architecture

## Architectural position

The Sarasota LGBT Archive Public Portal is the public access and publication layer for the archive. It is separate from the Archive OS preservation system.

## Major components

1. Public website
2. Custom CMS/admin interface
3. Authentication and role-based access system
4. Publication and exhibit system
5. Media and image derivative system
6. Public submission system
7. Takedown and correction request system
8. Dashboard and metrics system
9. Operations and integrations registry

## Application stack

- Next.js application
- TypeScript
- Prisma ORM
- SQLite for early local development
- PostgreSQL for production
- Tailwind CSS
- Sharp image processing
- S3-compatible object storage for web derivatives
- Matomo analytics
- SMTP/SES transactional email

## Storage boundaries

The portal may store:

- web derivatives
- captions
- public-facing metadata
- publication text
- exhibit structures
- public submissions
- correction and takedown records
- dashboard metrics
- access/audit logs

The portal must not store:

- preservation masters
- unredacted donor agreements
- restricted donor PII unless absolutely required for portal operations
- chain-of-custody originals
- full preservation event logs
- forensic disk images
- private archival deposits

## Data flow

Archive OS produces approved web derivatives and curated metadata. The portal imports or receives those derivatives and metadata, then applies publication, privacy, access, and representation rules before display.

## Deployment model

Initial production target:

- Hetzner VPS
- Dockerized Next.js app
- PostgreSQL database
- Backblaze B2 media bucket
- Cloudflare DNS/CDN/SSL
- GitHub Actions deployment

## Non-goals

The portal is not:

- a full archival repository
- a replacement for the Archive OS
- a preservation system
- a donor management system
- a social network
- a generic CMS
