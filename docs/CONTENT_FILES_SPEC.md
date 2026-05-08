# Content Files Specification

## Purpose

Slice 5 uses a static-first, Git-driven content model.

Public content is stored in repository files, edited locally, committed to GitHub, and deployed through the hosting provider.

This content model supports the first public launch without requiring a production database-backed CMS.

## Content root

All launch content should live under:

```text
content/
```

## Required directory structure

```text
content/
  site/
    navigation.json
    footer.md
    announcement.md

  pages/
    home.md
    about.md
    project-overview.md
    contact.md
    contribute.md
    events.md

  calls-to-action/
    donors.md
    volunteers.md
    oral-histories.md

  legal/
    privacy-notice.md
    no-upload-notice.md
    accessibility.md

  data/
    contact-inquiry-types.json
    site-settings.json
```

## Page front matter

Each page Markdown file must include YAML front matter.

Required fields:

```yaml
title: "Page title"
slug: "page-slug"
summary: "Short page summary."
status: "published"
showInNavigation: true
seoTitle: "SEO title"
seoDescription: "SEO description"
```

Optional fields:

```yaml
heroTitle: "Hero title"
heroSummary: "Hero summary"
order: 1
```

## Status values

Allowed Slice 5 status values:

- draft
- published

Draft pages must not render publicly.

## Slug rules

- home page uses slug: "/"
- other pages use lowercase hyphenated slugs
- slugs must be unique
- slugs should not include file extensions

## Navigation

Primary navigation is controlled by:

```text
content/site/navigation.json
```

Each navigation item should include:

- label
- href
- order
- visible

## Site settings

General settings are controlled by:

```text
content/data/site-settings.json
```

This file should include:

- siteName
- shortName
- tagline
- contactEmailLabel
- launchMode
- acceptsUploads

For Slice 5, `acceptsUploads` must be false.

## Contact inquiry types

Contact inquiry options are controlled by:

```text
content/data/contact-inquiry-types.json
```

Required categories:

- general
- volunteering
- oral-history-interest
- donation-interest
- press-media
- correction
- other

## Required public messaging

Slice 5 content must clearly state:

- the archive is seeking donors and funding supporters
- the archive is seeking volunteers
- the archive is seeking oral history participants
- the website is not yet accepting direct uploads of archival materials
- sensitive or confidential materials should not be sent through the contact form

## Legal and policy notices

The following content files must exist:

- privacy-notice.md
- no-upload-notice.md
- accessibility.md

These are not full legal instruments. They are launch-stage public notices.

## Implementation expectations

The application should:

- read Markdown files from the content directory
- parse front matter
- render published pages only
- exclude draft pages from public routing
- build navigation from navigation.json
- render footer.md in the shared footer
- render announcement.md only when enabled by the application or content logic

## Non-goals for Slice 5

Do not implement:

- browser-based editing
- database-backed content storage
- public file uploads
- archival ingest
- donor agreement workflows
- oral-history scheduling workflows
- complex access control for content files
