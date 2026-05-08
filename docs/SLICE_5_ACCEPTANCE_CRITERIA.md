# Slice 5 Acceptance Criteria

## Purpose

Slice 5 is the first public launch threshold.

At the end of Slice 5, the Sarasota LGBT Archive Public Portal must function as a publicly accessible informational website with a minimal CMS, contact form, authentication system, protected admin area, and coherent visual theme.

## Public pages required

The following pages must exist and render in production:

- /
- /about
- /project-overview or equivalent
- /contact
- /contribute or equivalent
- /events or equivalent placeholder page

Each page must:

- render without crashing
- be mobile responsive
- use the shared site theme
- use the shared header/footer
- include navigation
- include accessible typography and contrast

## Theme requirements

The theme must include:

- SVG logo in header
- responsive navigation
- mobile menu behavior
- typography scale
- spacing system
- accessible color contrast
- form styles
- button styles
- card styles
- footer layout
- basic homepage sections

The theme does not need to be visually final.

## CMS requirements

The archivist must be able to:

- sign in
- view page list
- create page
- edit page
- publish/unpublish page
- change title
- change slug
- change summary
- change body content
- change navigation visibility

The CMS may initially use:

- Markdown
- simple rich text
- textarea editing

The CMS does not yet need:

- block editing
- version diffing
- scheduling
- collaborative editing
- media galleries

## Contact form requirements

The contact form must:

- work in production
- validate input
- reject empty submissions
- reject malformed email addresses
- avoid file uploads
- include spam protection
- include privacy notice
- provide success state
- provide error state

Acceptable temporary implementations:

- database-backed contact messages
- SMTP email forwarding
- transactional email provider

The form must not:

- expose internal email addresses publicly
- accept archival uploads
- act as a donor-ingest workflow

## Authentication requirements

The system must support:

- login
- logout
- protected admin routes
- server-side session validation
- protected CMS actions

Public users must not:

- access admin routes
- access unpublished drafts
- access contact-message review interfaces

## Deployment requirements

The system must:

- deploy from GitHub
- use HTTPS
- load on a public domain or temporary deployment URL
- document environment variables
- document deployment process
- document rollback/redeploy process

## Production verification checklist

The following must be verified manually:

- homepage loads in production
- navigation works
- mobile navigation works
- SVG logo renders correctly
- login works
- logout works
- admin routes redirect unauthenticated users
- CMS edits persist correctly
- published pages render publicly
- unpublished pages are not public
- contact form submits correctly
- contact form failure state works
- no sensitive environment variables exposed client-side

## Required verification commands

- npm install
- npm run lint
- npx tsc --noEmit
- npm run build
- npx prisma validate

## Explicit non-goals for Slice 5

Do not implement yet:

- archival object publication
- media upload workflows
- donor submission workflows
- oral-history intake workflows
- takedown workflows
- correction workflows
- public search
- exhibit system
- timeline system
- S3 media workflows
- Archive OS synchronization
- full analytics stack
- production Docker hardening
