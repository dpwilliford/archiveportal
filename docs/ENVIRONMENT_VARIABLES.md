# Environment Variables

## Principle

All secrets, credentials, service URLs, and deployment-specific configuration must be provided through environment variables.

Do not hardcode secrets into source code.

Do not commit production secrets into Git.

## Local development

Local development should use:

- .env
- .env.local
- .env.development

These files must be gitignored where appropriate.

## Production

Production secrets must be configured through:

- hosting provider secret management
- deployment environment variables
- CI/CD secret management

## Required variables for Slice 5

### Database

DATABASE_URL

Purpose:

- Prisma database connection
- SQLite locally
- PostgreSQL in production

Examples:

SQLite local:

DATABASE_URL="file:./dev.db"

PostgreSQL production:

DATABASE_URL="postgresql://USER:PASSWORD@HOST:5432/DATABASE"

## Authentication

AUTH_SECRET

Purpose:

- session signing
- authentication security

Requirements:

- long random secret
- production-only secure value
- never committed to Git

## Site URL

NEXT_PUBLIC_SITE_URL

Purpose:

- canonical public URL
- absolute links
- metadata generation

Example:

NEXT_PUBLIC_SITE_URL="https://example.org"

## Contact form

CONTACT_FORM_RECIPIENT

Purpose:

- destination email for contact messages

Example:

CONTACT_FORM_RECIPIENT="archive@example.org"

## SMTP or email provider

SMTP_HOST
SMTP_PORT
SMTP_USER
SMTP_PASSWORD
SMTP_FROM_EMAIL

Purpose:

- contact-form delivery
- authentication-related email if implemented

## Optional future variables

### Backblaze B2 or S3-compatible storage

S3_ENDPOINT
S3_REGION
S3_BUCKET
S3_ACCESS_KEY_ID
S3_SECRET_ACCESS_KEY

### Matomo

MATOMO_URL
MATOMO_SITE_ID

### Rate limiting

RATE_LIMIT_SECRET

### Error monitoring

SENTRY_DSN

### Cloudflare

CLOUDFLARE_API_TOKEN

## Client-side exposure rules

Only variables intentionally exposed to the browser may use NEXT_PUBLIC_ prefixes.

Secrets must never use NEXT_PUBLIC_.

## Documentation requirements

Every external dependency must document:

- required environment variables
- local-development setup
- production setup
- fallback behavior
- failure behavior

## Verification

At minimum verify:

- app boots with expected environment variables
- production build succeeds
- secrets are not exposed client-side
- contact form works with configured email settings
- authentication works with configured secrets
