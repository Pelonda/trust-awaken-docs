# Identity API

## Authentication Endpoints

- POST /api/v1/auth/login
- POST /api/v1/auth/logout
- POST /api/v1/auth/forgot-password
- POST /api/v1/auth/reset-password
- GET /api/v1/auth/me
- POST /api/v1/auth/refresh

## Authorization Endpoints

- GET /api/v1/auth/roles
- GET /api/v1/auth/permissions

## Notes

- All public API responses should use UUIDs where applicable.
- Authentication endpoints must return consistent error formats.