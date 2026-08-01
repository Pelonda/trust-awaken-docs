# Identity Database

## Core Tables

- users
- roles
- permissions
- role_user
- permission_role
- user_sessions
- password_reset_tokens
- mfa_devices

## Notes

- Internal relationships use BIGINT primary keys.
- Public exposure uses UUID.
- Identity tables must be designed for future multi-organization support.
- Recipient data may be separated from normal user data if needed later.