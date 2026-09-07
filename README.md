# package-mes-basic-roles-accelerator

**Version:** 0.0.1
**Platform:** Fuuz ≥ 2024.7.0
**Spec Version:** 2.0.0

---

## Overview

This package delivers the standard Fuuz MES (Manufacturing Execution System) role and access control configuration for shop floor users. It seeds `Role`, `AccessControlPolicy`, and `AccessControlPolicyGroup` records aligned to the four core MES personas: Factory, Production, Receiving, and WMS — enabling rapid user provisioning for manufacturing environments without manual role configuration.

This is a data-only package (no flows, screens, or custom models). It imports directly into the Fuuz platform's built-in access control system and is designed to be paired with `application-mes-accelerator` or `application-wms-accelerator`.

---

## Package Contents

```
mes-basic-roles/
├── manifest.json
├── definition.json
├── package-data.json
└── data/                        10 seed data files
```

---

## Included Roles

| Role ID | Name | Intended Users |
|---------|------|----------------|
| `factory` | Factory | General factory floor users; access to production and machine monitoring screens |
| `production` | Production | Production operators focused on work order execution and production recording |
| `receiving` | Receiving | Warehouse receiving personnel; access to inbound shipment and receiving screens |
| `wms` | WMS | Warehouse management system users; inventory, transfers, and fulfillment operations |

---

## Included Access Control Policy Groups

| Group | Purpose |
|-------|---------|
| Operator | Standard shop floor operator access — control panel, production entry, mode changes |
| Supervisor | Elevated access for supervisors — includes operator access plus reporting, approval, and override capabilities |
| Receiving | Scoped access for receiving workflows — inbound shipments, receipt confirmation, and inventory |

---

## Included Access Control Policies

| Policy ID | Name | Description |
|-----------|------|-------------|
| `controlPanelAccess` | Control Panel Access | Allows operator-level interaction with the workcenter control panel (mode changes, production recording, scrap entry) |
| `readOnlyAccess` | Read Only Access | View-only access for observers and auditors; no mutations |
| `receiving` | Receiving | Scoped access for receiving workflows |
| `supervisor` | Supervisor | Elevated permissions for supervisors, including approval actions and configuration views |

---

## Role → Policy Group Assignments

| Role | Policy Group |
|------|-------------|
| Factory | Operator |
| Production | Operator |
| Receiving | Receiving |
| WMS | Operator |

---

## Installation

1. Import via Fuuz Package Manager — no pre-configuration required
2. Seed data applies immediately; roles and policies are created if they do not already exist
3. Assign roles to users via the Fuuz user management interface
4. Recommended: install alongside `application-mes-accelerator` or `application-wms-accelerator` so role home screens and menus are populated

---

## Dependencies

- **Fuuz Platform** ≥ 2024.7.0
- Designed for use with `application-mes-accelerator`, `application-mes-core-accelerator`, or `application-wms-accelerator`
- No custom data models or external dependencies

---

*Built on the [Fuuz Industrial Operations Platform](https://fuuz.com)*

## Service levels

No service level agreement applies to anything published here. It becomes a supported
deliverable only once it has been implemented by a Fuuz services professional or an
approved Fuuz partner.
