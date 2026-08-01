# Registration API

## Endpoint

POST /api/v1/public/register

---

## Request

```json
{
  "organization": {
    "displayName": "Global CyberSafe",
    "legalName": "Global CyberSafe",
    "organizationType": "nonprofit",
    "country": "US"
  },
  "owner": {
    "firstName": "John",
    "lastName": "Doe",
    "email": "admin@example.com",
    "password": "StrongPassword123!"
  }
}
```

---

## Success Response

HTTP 201

```json
{
  "success": true,
  "organization": {
    "uuid": "...",
    "displayName": "Global CyberSafe"
  },
  "owner": {
    "uuid": "...",
    "email": "admin@example.com"
  }
}
```

---

## Errors

400

Validation

401

Unauthorized

409

Organization Slug Exists

422

Validation Error