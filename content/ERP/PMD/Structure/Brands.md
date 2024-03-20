+++
title = 'Brands'
date = 2024-01-07T22:06:44-03:00
draft = false
weight = 4
+++

This entity represents all of the Brands.

The brand can be set to a **Case Product** to identify that product.

---

## Fields

**Name:** Simply the full name of the brand.
{{% expand title="**Details**" %}}
- Text
- One
- Required
{{% /expand %}}

**Code:** A unique code identifying the brand.
{{% expand title="**Details**" %}}
- Text
- One
- Required
- Unique
- No empty spaces at the start nor the end
{{% /expand %}}

---

## Permissions

| Entity | Admins |
| --- | --- |
| Create | Always |
| Access | Always |
| Edit | Always |
| Delete | Always |
| Audit logs | Doesn't apply |
| Import | {{% icon icon="check" %}} |
| Eport | {{% icon icon="check" %}} |

| Field | Admins |
| --- | --- |
| Name | Read/Write |
| Code | Read/Write |