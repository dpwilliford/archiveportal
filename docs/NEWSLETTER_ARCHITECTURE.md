# Newsletter Architecture

## Purpose

The Sarasota LGBT Archive newsletter serves two related functions:

1. Subscriber communication and institutional outreach.
2. Permanent born-digital publication and archival record.

Each issue is both:

- an email campaign distributed to subscribers; and
- a publicly accessible publication preserved at a stable URL.

The newsletter is treated as a serial publication rather than a transient marketing artifact.

## Phase 1: Subscriber Collection at Site Launch

Newsletter signup must be available from the first public launch of the website.

The mailing platform itself may be deployed later, but the archive must begin collecting and preserving subscriber relationships immediately.

### Launch Requirements

- newsletter signup form
- consent checkbox
- double opt-in confirmation
- confirmation email
- local storage of subscriber records
- timestamped consent records
- export capability for later import into Listmonk

## Phase 2: Mailing Platform Deployment

Within one to two months after launch, the archive will deploy:

- Listmonk (self-hosted newsletter platform)
- Amazon SES (outbound email delivery)

Confirmed subscribers collected during Phase 1 will be imported into Listmonk with all available consent metadata.

## Subscriber Data Model

The portal must maintain structured subscriber records with at least the following fields:

- id
- email
- first_name
- status (pending, confirmed, unsubscribed)
- signup_timestamp
- confirmation_timestamp
- consent_text_version
- source_page
- confirmation_token
- unsubscribe_timestamp
- notes

Optional fields:

- ip_address
- user_agent
- referral_source

## Double Opt-In Workflow

1. Visitor submits email address.
2. Record is created with status = pending.
3. Confirmation email is sent.
4. Visitor clicks unique confirmation link.
5. Status is updated to confirmed.
6. Confirmation timestamp is recorded.

No subscriber may be added to the mailing list until confirmation is completed.

## Consent Requirement

The signup form must include an explicit statement such as:

"I would like to receive occasional email updates from the Sarasota LGBT Archive. I understand that I may unsubscribe at any time."

The exact version of the consent language accepted by the subscriber must be recorded.

## Listmonk Integration

Once Listmonk is operational, the website signup form may either:

1. Continue storing records locally and synchronize to Listmonk; or
2. Submit directly to the Listmonk API.

In either case, the portal remains the authoritative source for consent records.

## Amazon SES

Amazon SES is used as the SMTP transport layer for:

- confirmation emails
- transactional notifications
- newsletter campaign delivery

SES provides outbound delivery only and does not constitute the system of record for subscriber data.

## Public Publication Requirement

Every newsletter issue must also be published on the public website at a stable URL, for example:

/newsletter/2026-07-launch-issue

Each issue should include:

- title
- issue number
- publication date
- summary
- HTML content
- downloadable PDF
- citation metadata

## Preservation Requirement

For each published issue, the archive should preserve:

- source content
- rendered HTML
- PDF derivative
- images and media
- metadata
- campaign statistics where appropriate

These materials may be ingested into the Archive Operating System for long-term preservation.

## Service Dependencies

- Listmonk
- PostgreSQL
- Amazon SES
- Docker
- Cloudflare DNS/SSL
- Archive Portal API integration

## Governing Principle

Subscriber addresses, consent records, and newsletter content are institutional assets.

The system must preserve:

- data ownership
- exportability
- consent evidence
- long-term publication access
- archival preservation
