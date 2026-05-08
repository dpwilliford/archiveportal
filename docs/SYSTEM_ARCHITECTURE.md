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

## External dependency architecture

The portal must not assume that third-party services integrate seamlessly by default.

Every external dependency must be treated as a controlled integration boundary.

All external dependencies must:

- be wrapped behind internal service modules or adapters
- avoid direct vendor calls scattered throughout application routes or components
- have documented environment variables
- have documented setup procedures
- have documented local-development fallback behavior
- have documented production verification procedures
- have documented privacy and data-handling notes
- have defined failure behavior
- have a replacement or migration path documented where possible
- expose meaningful logging and error reporting

Examples of external dependencies include:

- PostgreSQL providers
- SMTP/email providers
- Backblaze B2
- Cloudflare
- Matomo
- Vercel
- authentication providers
- rate-limiting systems
- spam-protection systems
- analytics systems

## Operations and integrations registry

The portal must maintain an operations and integrations registry.

Each integration record should include:

- integration name
- purpose
- service category
- environment variables required
- production status
- development fallback behavior
- privacy classification
- data retention considerations
- external accounts required
- billing owner or responsible administrator
- failure modes
- replacement procedure
- verification checklist
- operational notes

## Deployment model

Initial production target:

- Hetzner VPS
- Dockerized Next.js app
- PostgreSQL database
- Backblaze B2 media bucket
- Cloudflare DNS/CDN/SSL
- GitHub Actions deployment

Early launch deployments may temporarily use:

- Vercel Hobby
- Cloudflare Pages
- low-cost managed PostgreSQL providers

provided that:

- persistence limitations are documented
- rollback procedures are documented
- data boundaries remain enforced
- migration to long-term infrastructure remains possible

## Non-goals

The portal is not:

- a full archival repository
- a replacement for the Archive OS
- a preservation system
- a donor management system
- a social network
- a generic CMS
