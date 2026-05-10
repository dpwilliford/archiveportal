# Technical Specifications

## Objective

Build a standards-aligned archival operating environment capable of supporting real-world archival work from donor intake through long-term preservation and public access.

## Minimum Viable Archive Requirements

The system must be able to:

1. Accept a donation.
2. Record legal and rights documentation.
3. Assign an accession number.
4. Register physical and digital objects.
5. Generate SHA-256 checksums.
6. Create BagIt packages.
7. Record preservation events.
8. Track replicated storage locations.
9. Produce collection descriptions.
10. Publish public finding aids.

## Core Data Entities

- Donor
- Accession
- Collection
- Physical Container
- Digital Object
- Rights Record
- Preservation Event
- Storage Location

## Technical Stack (Initial)

- Next.js
- TypeScript
- Tailwind CSS
- Prisma
- SQLite (prototype)
- PostgreSQL (production)
- Object storage (S3-compatible)

## Non-Negotiable Constraints

- Offline-first field operations
- Open formats and exportability
- Separation of preservation masters and access derivatives
- Rights enforcement before publication
- Full auditability of preservation actions

## Acceptance Criteria

The archive is operational when an archivist can conduct a field session, create a BagIt package, ingest it into the repository, and publish a collection description and selected derivatives through the public portal.
