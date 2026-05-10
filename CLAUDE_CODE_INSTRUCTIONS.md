# Claude Code Instructions

## Development Philosophy

This repository is specification-driven. All development must be grounded in the planning documents contained in the repository.

## Primary Goal

Build a standards-aligned archival operating environment capable of supporting real-world archival operations for the Sarasota LGBT Archive.

## Architectural Components

1. Intake Workbench (IWB)
2. Archive Operating System (AOS)
3. Public Portal (PP)

## Development Rules

1. Preserve all existing functionality unless explicitly instructed otherwise.
2. Work in small, verifiable slices.
3. Provide a written implementation plan before coding.
4. Reuse established open-source libraries rather than reimplementing mature functionality.
5. Use open, exportable formats.
6. Maintain comprehensive tests and documentation.
7. Ensure all preservation-significant actions are auditable.

## Standard Verification Commands

- npm run lint
- npx tsc --noEmit
- npm test
- npm run build

## Definition of Done

A feature is complete only when:

- Code is implemented.
- Tests pass.
- Documentation is updated.
- Existing functionality is preserved.
- Acceptance criteria are satisfied.
