# Content Model

## Purpose

This document defines the principal intellectual and administrative entities used by the Sarasota LGBT Archive Public Portal.

The portal is a publishing and interpretation platform rather than a generic blog or CMS. Each entity represents a distinct class of documentary object with specific metadata, relationships, and editorial requirements.

## Design Principles

- Stable identifiers for every entity.
- Human-readable slugs for public URLs.
- Explicit editorial status values.
- Clear relationships between entities.
- Separation between public metadata and restricted archival metadata.
- Exportability to standard formats.

## Editorial Status Values

All publishable entities should support:

- draft
- review
- approved
- published
- archived

## Core Content Types

### Page

Used for informational pages such as About, Mission, Donate, and Privacy Policy.

Required fields:

- id
- title
- slug
- summary
- body
- status
- published_at
- updated_at

Canonical URL:

- `/{slug}`

### Publication

Used for essays, articles, reports, books, and dossiers.

Required fields:

- id
- title
- slug
- summary
- body
- publication_date
- status
- canonical_url
- citation_text

Relationships:

- authors (Person)
- media_assets (MediaAsset)
- tags

Canonical URL:

- `/publications/{slug}`

### NewsletterIssue

Used for serial newsletter publications.

Required fields:

- id
- issue_number
- title
- slug
- summary
- body
- publication_date
- status
- citation_text
- pdf_url

Relationships:

- related_publications (Publication)
- media_assets (MediaAsset)

Canonical URL:

- `/newsletter/{slug}`

### TimelineEntry

Used for chronological historical entries.

Required fields:

- id
- title
- start_date
- end_date
- narrative
- status

Relationships:

- people (Person)
- organizations (Organization)
- places (Place)
- media_assets (MediaAsset)

Canonical URL:

- `/timeline`

### Event

Used for public programs and institutional events.

Required fields:

- id
- title
- slug
- summary
- description
- start_datetime
- end_datetime
- location
- status

Canonical URL:

- `/events/{slug}`

### Exhibit

Used for curated digital exhibitions.

Required fields:

- id
- title
- slug
- summary
- body
- status

Relationships:

- media_assets (MediaAsset)
- publications (Publication)

Canonical URL:

- `/exhibits/{slug}`

### MediaAsset

Used for images, audio, video, and downloadable files.

Required fields:

- id
- title
- file_type
- storage_key
- alt_text
- rights_statement
- status

### Person

Authority record for individuals.

Required fields:

- id
- display_name
- slug
- biography

Canonical URL:

- `/people/{slug}`

### Organization

Authority record for organizations.

Required fields:

- id
- name
- slug
- summary

Canonical URL:

- `/organizations/{slug}`

### Place

Authority record for geographic locations.

Required fields:

- id
- name
- slug
- summary

Canonical URL:

- `/places/{slug}`

## Administrative Types

### Subscriber

Used for newsletter signup and consent tracking.

Required fields:

- id
- email
- first_name
- status
- signup_timestamp
- confirmation_timestamp
- consent_text_version
- source_page
- unsubscribe_timestamp

### ContactMessage

Used for public inquiries.

Required fields:

- id
- name
- email
- subject
- message
- submitted_at
- status

## MVP Scope

The initial public launch requires only:

- Page
- Publication
- Subscriber
- ContactMessage

Other content types may be introduced incrementally.
