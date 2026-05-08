# Permission Matrix

## Principle

Permissions must protect privacy, consent, moderation authority, and community safety.

Public visibility must never be assumed.

Permissions must be explicit rather than inferred.

## Roles

Initial roles:

- public_visitor
- registered_community_member
- verified_researcher
- donor
- volunteer
- contributor
- editor
- board_member
- archivist_owner
- administrator

## Permission domains

The system must support permissions for:

- viewing public pages
- viewing restricted pages
- viewing thumbnails
- viewing full media
- downloading media
- creating drafts
- editing drafts
- publishing content
- withdrawing content
- managing navigation
- reviewing contact messages
- reviewing correction requests
- reviewing takedown requests
- managing users
- managing integrations
- viewing dashboards
- managing roles

## Matrix

| Permission | Public | Registered | Researcher | Donor | Volunteer | Contributor | Editor | Board | Archivist | Admin |
|---|---|---|---|---|---|---|---|---|---|---|
| View public pages | yes | yes | yes | yes | yes | yes | yes | yes | yes | yes |
| Submit contact form | yes | yes | yes | yes | yes | yes | yes | yes | yes | yes |
| View restricted pages | no | limited future | limited future | limited future | limited future | limited future | yes | yes | yes | yes |
| Create draft pages | no | no | no | no | no | limited future | yes | limited future | yes | yes |
| Edit own drafts | no | no | no | no | no | limited future | yes | limited future | yes | yes |
| Publish content | no | no | no | no | no | no | yes | limited future | yes | yes |
| Withdraw content | no | no | no | no | no | no | yes | limited future | yes | yes |
| Review contact messages | no | no | no | no | no | no | yes | limited future | yes | yes |
| Review correction requests | no | no | no | no | no | no | yes | limited future | yes | yes |
| Review takedown requests | no | no | no | no | no | no | limited future | limited future | yes | yes |
| Manage navigation | no | no | no | no | no | no | yes | no | yes | yes |
| View admin dashboard | no | no | no | no | no | no | yes | yes | yes | yes |
| Manage integrations | no | no | no | no | no | no | no | no | yes | yes |
| Manage users | no | no | no | no | no | no | no | no | yes | yes |
| Manage roles | no | no | no | no | no | no | no | no | yes | yes |

## Slice 5 requirements

By Slice 5:

- public visitors must not access /admin routes
- authenticated sessions must exist
- admin navigation must be protected
- role checks must exist server-side
- role checks must not depend only on hidden client-side UI
- contact-message access must be restricted
- unpublished drafts must not be publicly routable

## Explicit material requirements

Explicit material must:

- never be public by default
- require authentication
- require age affirmation where appropriate
- suppress public thumbnails unless approved
- disable public indexing where appropriate
- log access where implemented
- support archivist review before publication

## Future expansion

Future slices may add:

- collection-specific permissions
- embargo windows
- time-based restrictions
- donor-controlled visibility
- temporary researcher access
- volunteer workflow permissions
- exhibit-specific editorial teams
- external contributor workflows
