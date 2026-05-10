# System Architecture

## Overview

The Sarasota LGBT Archive software stack consists of three tightly integrated applications:

1. **Intake Workbench (IWB)** – Offline-first desktop application for donor intake, oral history capture, digitization, and born-digital transfer.
2. **Archive Operating System (AOS)** – Preservation-centered repository and system of record.
3. **Public Portal (PP)** – Public-facing website for finding aids, oral histories, exhibits, timelines, and publications.

Together these components form the Archival Operating Environment (AOE).

## Architectural Flow

Community Member / Donor
→ Intake Workbench (creates Submission Information Package)
→ Archive Operating System (ingests and preserves as Archival Information Package)
→ Public Portal (publishes approved Dissemination Information Packages)

## Core Standards

- OAIS (ISO 14721)
- PREMIS
- DACS
- EAD
- EAC-CPF
- Dublin Core
- BagIt
- NDSA Levels of Digital Preservation
- FADGI
- WCAG

## Functional Responsibilities

### Intake Workbench

- Donor intake and rights capture
- Oral history management
- Digitization session management
- Born-digital transfer
- Checksum generation
- Technical metadata extraction
- BagIt packaging
- Offline synchronization

### Archive Operating System

- Accession control
- Arrangement and description
- Authority control
- Rights and restrictions management
- PREMIS event logging
- Fixity verification
- Storage replication tracking
- Export and interoperability

### Public Portal

- Collection and finding aid pages
- Search and browse
- Oral history streaming and transcripts
- Digital exhibits
- Timelines and publications
- Donation and newsletter forms

## Guiding Constraint

Every preservation-significant action must generate durable evidence of what was done, when it was done, by whom, and with what result.
