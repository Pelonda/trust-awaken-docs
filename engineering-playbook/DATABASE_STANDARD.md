# Database Standard

## Rules

One table = One responsibility.

Never create "God Tables."

Every business table includes

- id
- uuid
- created_at
- updated_at
- deleted_at

unless immutable.

---

## Foreign Keys

Always

organization_id

user_id

role_id

Never

orgId

userid