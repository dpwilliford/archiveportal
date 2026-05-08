# Sarasota LGBT Archive Public Portal

## Purpose

This repository defines and will implement the public-facing web portal for the Sarasota LGBT Archive.

The portal is a publication, access, engagement, event, exhibit, and community-submission platform. It is not the long-term preservation repository and is not the system of record for preservation masters, donor records, chain-of-custody documentation, or preservation events.

The portal publishes curated derivatives and public-facing interpretation from the archive, including:

- online exhibits
- essays and features
- newsletters and publication issues
- digital books and dossiers
- timelines
- collection highlights
- image and video galleries
- public events
- volunteer resources
- community submissions
- correction and takedown request workflows

## Foundational constraint

The portal must be privacy-first, community-accountable, visually rich, mobile-responsive, and usable by a nontechnical archivist.

## Separation from Archive OS

The Archive OS remains the preservation authority. It stores preservation masters, donor files, restricted records, PREMIS events, fixity logs, and chain-of-custody documentation.

The portal stores and serves only public or access-controlled derivatives, curated metadata, publication content, dashboard metrics, public submissions, and review queues.

## Initial stack

- Next.js
- TypeScript
- Tailwind CSS
- Prisma
- SQLite for local prototype
- PostgreSQL for production
- Backblaze B2 or other S3-compatible storage for web derivatives
- Sharp for image derivative generation
- Auth.js or custom session authentication
- Matomo for privacy-preserving analytics
- Amazon SES or SMTP-compatible transactional email
- Docker for deployment
- GitHub Actions for CI/CD
- Cloudflare for DNS, SSL, and caching

## Development method

This project must be developed as thin vertical slices. Each slice must produce a visible, testable feature. Do not build a generic CMS. Build a custom archival publication CMS for this specific public portal.
