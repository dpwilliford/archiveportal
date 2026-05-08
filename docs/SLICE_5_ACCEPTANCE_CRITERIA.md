# Slice 5 Acceptance Criteria

## Purpose

Slice 5 is the first public launch threshold.

At the end of Slice 5, the Sarasota LGBT Archive Public Portal must function as a publicly accessible informational website with a file-based content management workflow, contact form, authentication system, protected admin area, and coherent visual theme.

## Strategic implementation decision

Slice 5 uses a static-first, Git-driven publishing model.

Public content is edited locally in Markdown, MDX, JSON, or equivalent structured content files and then deployed automatically through GitHub.

This approach reduces infrastructure complexity and allows the project to launch quickly without requiring a production database-backed CMS.

A database-backed editorial CMS may be introduced in later slices after the public website is stable.

## Public pages required

The following pages must exist and render in production:

- /
- /about
- /project-overview or equivalent
- /contact
- /contribute or equivalent
- /events or equivalent placeholder page

The homepage and related launch pages must explicitly invite:

- donors and funding supporters
- volunteers
- oral history participants

The site must clearly state that the website is not yet accepting direct uploads of archival materials.

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

## File-based content management requirements

The archivist must be able to:

- edit homepage content locally
- edit page titles
- edit slugs
- edit summaries
- edit body content
- control navigation visibility
- create new pages by adding or editing structured content files
- publish changes by committing to Git and triggering deployment

Acceptable content formats:

- Markdown
- MDX
- JSON
- YAML front matter with Markdown body

The Slice 5 content system does not yet need:

- browser-based page editing
- database persistence for pages
- block editing
- revision diffing
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

Required inquiry categories:

- general inquiry
- volunteering
- oral history interest
- donation interest
- press or media
- correction
- other

Preferred delivery method:

- send messages to a Google Workspace account dedicated to the archive

The form may:

- send directly via SMTP
- use a transactional email provider
- use a documented temporary email-forwarding mechanism

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
- protected administrative actions

Public users must not:

- access admin routes
- access unpublished drafts or internal content
- access contact-message review interfaces

## Deployment requirements

The system must:

- deploy from GitHub
- use HTTPS
- load on a purchased custom domain or temporary deployment URL during setup
- document environment variables
- document deployment process
- document rollback/redeploy process

Recommended hosting model:

- Vercel Hobby or Cloudflare Pages
- Cloudflare DNS and SSL if desired
- Google Workspace for contact email delivery

## Production verification checklist

The following must be verified manually:

- homepage loads in production
- navigation works
- mobile navigation works
- SVG logo renders correctly
- login works
- logout works
- admin routes redirect unauthenticated users
- content changes made locally deploy correctly from GitHub
- public pages render correctly after deployment
- contact form submits correctly
- contact form failure state works
- no sensitive environment variables exposed client-side

## Required verification commands

- npm install
- npm run lint
- npx tsc --noEmit
- npm run build

## Explicit non-goals for Slice 5

Do not implement yet:

- database-backed page CMS
- archival object publication
- media upload workflows
- donor submission workflows
- oral-history intake workflows
- takedown workflows
- correction workflows beyond the contact form
- public search
- exhibit system
- timeline system
- S3 media workflows
- Archive OS synchronization
- full analytics stack
- production Docker hardening
