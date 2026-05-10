# CLAUDE.md

## Purpose

This repository implements the public-facing Archive Portal for the Sarasota LGBT Archive.

The Portal is not the preservation repository, not the system of record, and not the ingest environment. It publishes approved public derivatives, public metadata, interpretation, exhibits, essays, timelines, and access interfaces exported from Archive OS.

## System Boundary

The larger archival software system has three components:

1. Intake Workbench — offline-first field capture and SIP creation.
2. Archive OS — preservation authority, metadata system of record, rights system, finding-aid generator, and AIP manager.
3. Archive Portal — public dissemination layer for approved DIPs only.

Claude Code must treat Archive OS as the source of truth for preservation, donor records, restrictions, rights, identifiers, finding-aid approval, and publication state.

## Non-Negotiable Rules

Claude Code must not:

- store preservation masters in the Portal;
- expose donor legal identities unless explicitly present in approved public metadata;
- expose donor contact information;
- expose private consent forms;
- expose confidential agreements;
- expose restricted files or restricted metadata;
- expose internal processing notes;
- expose private audit logs;
- allow unreviewed oral histories to appear publicly;
- publish a digital object without a rights status;
- publish a finding aid without versioning;
- allow a derivative to replace or overwrite a preservation master;
- bypass Archive OS approval for public export;
- introduce a third-party SaaS dependency without explicit approval;
- weaken tests or remove tests merely to satisfy a build;
- proceed to later development slices unless instructed.

## Development Method

Development must proceed in thin vertical slices. Each slice must leave the site deployable.

Do not build a generic CMS. Build a specific archival publication portal for the Sarasota LGBT Archive.

## Required Verification

```bash
npm install
npm run lint
npx tsc --noEmit
npm test
npm run build
```

If a command does not exist yet, state that explicitly and do not claim it passed.
