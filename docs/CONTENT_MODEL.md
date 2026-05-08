# Content Model

## Core models

Minimum models:

- User
- Role
- Session
- Page
- Exhibit
- ExhibitSection
- Publication
- PublicationIssue
- Work
- Series
- DigitalBook
- BookSection
- Contributor
- Person
- Place
- MediaItem
- ImageDerivative
- VideoItem
- TimelineEntry
- CollectionHighlight
- Event
- VolunteerResource
- PublicSubmission
- CorrectionRequest
- TakedownRequest
- CommentMessage
- NewsletterSignup
- DashboardMetric
- IntegrationStatus
- AuditLog
- AccessLog

## Shared public content fields

Every public content model should include:

- id
- slug
- title
- summary
- body or structured content blocks
- status
- visibilityLevel
- minimumRoleRequired
- createdAt
- updatedAt
- publishedAt
- createdBy
- updatedBy
- reviewedBy
- rightsStatement
- citationText
- seoTitle
- seoDescription
- searchIndexingAllowed

## Publication status values

- draft
- internal_review
- scheduled
- published
- archived
- withdrawn
- under_review
- temporarily_restricted
