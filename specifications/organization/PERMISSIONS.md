# Organization Permissions Specification

## Purpose

This document defines the authorization model for the Organization module.

It specifies which platform roles are permitted to perform Organization-related operations.

---

# Roles

The Organization module supports the following roles.

## Platform Administrator

Platform Administrators manage all Organizations across the Trust AWAKEN platform.

Permissions include:

- Create Organizations
- View all Organizations
- Update all Organizations
- Archive Organizations
- Restore Organizations
- Transfer Ownership
- Assign Organization Owners
- View audit information

---

## Organization Owner

The Owner is the highest privileged user within an Organization.

Permissions include:

- View Organization
- Update Organization
- Manage Administrators
- Manage Operators
- Manage Viewers
- Manage Organization Settings
- Manage Branding
- View Reports

Restrictions:

- Cannot manage other Organizations.
- Cannot access Platform Administration.

---

## Organization Administrator

Administrators assist the Owner with daily management.

Permissions include:

- View Organization
- Update Organization
- Manage Users
- View Reports
- Manage Templates
- Manage Documents

Restrictions:

- Cannot transfer ownership.
- Cannot archive Organization.
- Cannot delete Organization.

---

## Organization Operator

Operators perform operational tasks.

Permissions include:

- View Organization
- Manage Documents
- Issue Credentials
- Verify Credentials

Restrictions:

- Cannot manage Organization settings.
- Cannot manage permissions.
- Cannot archive Organization.

---

## Organization Viewer

View-only role.

Permissions include:

- View Organization
- View Reports
- View Documents (where authorized)

Restrictions:

- No create
- No update
- No delete
- No administrative functions

---

# Permission Matrix

| Operation | Platform Admin | Owner | Admin | Operator | Viewer |
|-----------|:--------------:|:-----:|:-----:|:--------:|:------:|
| Create Organization | ✅ | ❌ | ❌ | ❌ | ❌ |
| View Organization | ✅ | ✅ | ✅ | ✅ | ✅ |
| Update Organization | ✅ | ✅ | ✅ | ❌ | ❌ |
| Archive Organization | ✅ | ❌ | ❌ | ❌ | ❌ |
| Restore Organization | ✅ | ❌ | ❌ | ❌ | ❌ |
| Transfer Ownership | ✅ | ✅ | ❌ | ❌ | ❌ |
| Manage Users | ✅ | ✅ | ✅ | ❌ | ❌ |
| Manage Branding | ✅ | ✅ | ❌ | ❌ | ❌ |
| Manage Settings | ✅ | ✅ | ❌ | ❌ | ❌ |
| View Audit Logs | ✅ | Limited | ❌ | ❌ | ❌ |

---

# Authorization Rules

Authorization is enforced using Role-Based Access Control (RBAC).

Every authenticated user belongs to one or more Organizations and is assigned one or more roles.

Permissions are evaluated within the context of the current Organization.

---

# Platform Rules

Platform Administrators may access every Organization.

Organization-level roles are restricted to their assigned Organization.

Cross-Organization access is denied unless explicitly authorized.

---

# Future Enhancements

Future versions may introduce:

- Custom Roles
- Fine-Grained Permissions
- Attribute-Based Access Control (ABAC)
- Temporary Permissions
- Approval Workflows
- Delegated Administration