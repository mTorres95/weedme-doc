+++
title = 'Profiles'
date = 2024-01-07T22:06:28-03:00
draft = false
weight = 6
+++

This entity represents the specific variety or **type** of cannabis 
plant with unique characteristics (**lineage**, **aroma and flavor**) called **Strains** and also **flavors** and **non-specific** 
configurations, grouped under **Non Strain**.

An example of a Strain Profile would be *Blue Iguana* and a Non Strain
Profile would be *Breath Raspberry Lemonade* or *Indica 20% Plus*.

The view for the records of this entity is under **PRODUCTS MASTER**
**DATA > Profiles**, which contains **Strain** and **Non Strain**.

---

## Fields

**Name:** The name of the profile.
{{% expand title="**Details**" %}}
- Text
- One
- Required
{{% /expand %}}

**Code:** The unique identifier for the profile.
{{% expand title="**Details**" %}}
- Text
- One
- Required
- Unique
- No empty spaces at the start nor end
{{% /expand %}}

**Type:** type of the profile, a choice with these three options:
- Strain
- Flavour
- Non Specific
{{% expand title="**Details**" %}}
- Choice > Predefined: "Profile Types"
- One
- Required
{{% /expand %}}

**Strain:** Details of the cannabis plant, including **Type**, 
**Lineage** and **Aroma & Flavor**.
{{% expand title="**Details**" %}}
- Nested
- One
- Required if `type == strain`
- Read/Write access if `type == strain`
- Fields:
    * **Type:**
        - Choice > Predefined: "Strain Types"
        - One
        - Required
    * **Profile:**
        - Text
        - One
        - Not required
    * **Aroma & Flavour:**
        - Nested
        - One
        - Not required
        - Fields:
            * **English:**
                - Text
                - One
                - Not required
            * **French:**
                - Text
                - One
                - Not required
{{% /expand %}}

**Configuration:** When there is no specific strain or a flavor, the
profile could have a customized configuration, for example: *Blend,*
*various, Mix, Strain Dependent..*
{{% expand title="**Details**" %}}
- Text
- One
- Required if `type != strain`
- Read/Write access if `type != strain`
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
| Name | Read/Write |
| Code | Read/Write |
| Type | Read/Write |
| Strain | Read/Write |
| Configuration | Read/Write |