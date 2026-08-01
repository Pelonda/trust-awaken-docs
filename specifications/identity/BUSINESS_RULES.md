# Identity Business Rules

## Rule 1
Every authenticated account must have a unique UUID.

## Rule 2
Platform Users and Organization Users are distinct actor types.

## Rule 3
Recipients are not treated as normal platform users.

## Rule 4
Passwords must never be stored in plain text.

## Rule 5
Every login attempt must be auditable.

## Rule 6
MFA is required for privileged accounts.

## Rule 7
Authorization must be role-based at minimum.

## Rule 8
Session expiration must be enforced.

## Rule 9
A single account may eventually belong to multiple organizations, but v1 may start with one.

## Rule 10
Identity owns authentication and authorization only.