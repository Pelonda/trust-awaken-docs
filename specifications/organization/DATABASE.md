# Organization Database Design

## Purpose

This document defines the database design for the Organization module.

The Organization table represents the root aggregate for tenant management within the Trust AWAKEN platform.

---

# Database Overview

The Organization aggregate is intentionally small.

Additional information is stored in dedicated tables to maintain normalization and support long-term scalability.

---

# Primary Table

## organizations

| Column | Type | Required | Description |
|---------|------|----------|-------------|
| id | BIGINT | Yes | Internal database identifier |
| uuid | UUID | Yes | Public identifier exposed through APIs |
| slug | VARCHAR(150) | Yes | Unique human-readable identifier |
| display_name | VARCHAR(255) | Yes | Organization display name |
| legal_name | VARCHAR(255) | Yes | Official legal name |
| organization_type | VARCHAR(50) | Yes | Organization type |
| status | VARCHAR(30) | Yes | Organization lifecycle status |
| owner_user_id | BIGINT | Yes | Owner of the organization |
| created_at | TIMESTAMP | Yes | Creation timestamp |
| updated_at | TIMESTAMP | Yes | Last update timestamp |
| deleted_at | TIMESTAMP | No | Soft delete timestamp |

---

# Primary Key

- id

---

# Public Identifier

- uuid

---

# Unique Constraints

- uuid
- slug

---

# Foreign Keys

owner_user_id

References:

users.id

On Update

Cascade

On Delete

Restrict

---

# Indexes

- uuid
- slug
- organization_type
- status
- owner_user_id

---

# Relationships

Organization

→ Owner (User)

One Organization has one Owner.

---

Future Relationships

Organization

→ Branding

Organization

→ Settings

Organization

→ Contacts

Organization

→ Addresses

Organization

→ Domains

Organization

→ Preferences

Organization

→ Security

Organization

→ Subscription

Organization

→ Features

---

# Soft Delete

Organizations use Soft Delete.

Records remain available for auditing.

---

# Data Integrity Rules

- UUID must be unique.
- Slug must be unique.
- Organization Type must be valid.
- Status must be valid.
- Every Organization must have an Owner.

---

# Performance Considerations

Indexes are created for:

- UUID lookups
- Slug lookups
- Organization Type filtering
- Status filtering
- Owner lookups

These indexes support fast API responses and administrative searches.

---

# Future Tables

Future versions may introduce:

- organization_branding
- organization_settings
- organization_contacts
- organization_addresses
- organization_domains
- organization_preferences
- organization_security
- organization_subscription
- organization_features

Each table will reference organizations.id.

---

# Migration Notes

The organizations table is intentionally minimal.

Business capabilities are added through related tables rather than expanding the primary table.