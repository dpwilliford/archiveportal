# Claude Code Working Instructions

Read the following documents before making any changes:

- README.md
- docs/MVP_SCOPE.md
- docs/SYSTEM_ARCHITECTURE.md
- docs/CONTENT_MODEL.md
- docs/DEVELOPMENT_ROADMAP.md
- docs/PHASE_1_SLICES.md
- docs/NEWSLETTER_ARCHITECTURE.md

## Governing Rules

1. Work on one slice only per session.
2. Do not implement future slices unless explicitly instructed.
3. Preserve all existing functionality.
4. Keep the application deployable after every change.
5. Do not introduce unnecessary abstractions.
6. Report all deferred work explicitly.
7. Run verification commands:
   - npm run lint
   - npx tsc --noEmit
   - npm run build

## Scope Discipline

The first objective is a functioning public website, not the complete institutional platform.

Do not add:

- Prisma
- PostgreSQL
- Authentication
- CMS features
- Upload systems
- Dashboards
- Collection search

unless the current slice explicitly requires them.
