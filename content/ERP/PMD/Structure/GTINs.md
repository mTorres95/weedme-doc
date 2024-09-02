+++
title = 'GTINs'
date = 2024-01-07T22:06:28-03:00
draft = false
weight = 7
+++

GTIN or **Global Trade Item Number**, bought from GS1, identifies the 
**Unit** and **Case Products**.

---

## Fields

**Unit GTIN:** 
{{% expand title="**Details**" %}}
- Text
- One
- Required
- Unique
- No empty spaces at the start nor end
{{% /expand %}}

**Short Unit GTIN:** 
{{% expand title="**Details**" %}}
- Text
- One
- Not required
- Unique
- No empty spaces at the start nor end
{{% /expand %}}

**Unit Product:** 
{{% expand title="**Details**" %}}
- Relationship to PMD > Products > Unit Products
- Filtered by `status == active`
- Link enabled
- Sorted by Label
- One
- Required if `GS1 publication > status == published`
- Unique
- Visible if `unit product not empty`
{{% /expand %}}

**Case GTINs:** 
{{% expand title="**Details**" %}}
- Nested
- Many
- Not required
- Fields:
    * **Pallet Code:**
        - Text
        - One
        - Required
        - No empty spaces at the start nor end 
    * **Quantity:**
        - Choice > [2, 6, 12, 24, 48]
        - One
        - Not required
    * **Case Product:**
        - Relationship to PMD > Products > Case Products
        - Filtered by `status == [active,warning]`
        - Link enabled
        - Sorted by Label
        - One
        - Not required
        - Visible if `case product not empty`
{{% /expand %}}

**Short Case GTIN:** 
{{% expand title="**Details**" %}}
- Text
- One
- Not required
- No empty spaces at the start nor end
{{% /expand %}}

**GS1 Publication:** 
{{% expand title="**Details**" %}}
- Nested
- One
- Required
- Fields:
    * **Status:**
        - Choice > [Not Published, Published]
        - One
        - Default value: Not Published
        - Required
        - Read Only
    * **Date:** Date when the GTIN has been published to the GS1 
    system with the product.    
        - Date
        - One
        - Default value: Current Date
        - Required if `status == published`
{{% /expand %}}

---

## Actions

No specific actions for this entity.

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
| Unit GTIN | Read/Write |
| Short Unit GTIN | Read/Write |
| Unit Product | Read Only |
| Case GTINs | Read/Write |
|  >> Case Product | Read Only |
| Short Case GTIN | Read/Write |
| GS1 Publication | Read/Write |
|  >> Status | Read Only |
