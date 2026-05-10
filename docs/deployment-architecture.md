# Deployment Architecture

## Environments

- Local Development
- Staging
- Production

## Deployment Flow

GitHub → GitHub Actions → Build → Deploy → DNS/CDN → Monitoring

## Hosting Principles

- Public derivatives only
- No preservation masters
- Environment variables for secrets
- Reproducible builds
