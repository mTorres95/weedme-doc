+++
title = 'Components'
date = 2024-01-07T22:06:05-03:00
draft = false
weight = 5
+++

This entity represents **all the material components that form part** 
**of the product**, such as packaging, labels, and cases, in all three
levels of products:

* **Atomic:** for example, a cone for a pre-roll
* **Unit:** for example, a tube
* **Case:** for example, a box


{{% notice style="grey" title=" " icon=" " %}}
It's important to know that this entity does not incluide information
about the cannabis component of the products, that is represented by
another entity called *Raw Materials*
{{% /notice %}}

An example of a Component would be *Cones - 109/26 Branded (Jware)*

The view for the records of this entity is under **PRODUCTS MASTER**
**DATA > Components**

---

## Fields

**Name:** The name of the component.
{{% expand title="**Details**" %}}
- Text
- One
- Required
{{% /expand %}}

**Level:** The product level where the component can be use for. More
than one level can be selected for a product.
- Atomic Product 
- Unit Product
- Case Product

{{% expand title="**Details**" %}}
- Choice
- Many
- Required
{{% /expand %}}

**Class:** Specific class or type of component. The classes can be 
created and updated as needed, it's not a fixed list.
{{% expand title="**Details**" %}}
- Relationship to PMD > Component Classes
- One
- Required if `status == active`
- Allow to create and to edit
- Sorted by label
{{% /expand %}}

**Weight:** The weight of the component in grams. It's always required
but the value can be zero for labels for example.
{{% expand title="**Details**" %}}
- Decimal
- One
- Required
- Cannot be negative
- Override Label: Weight (g)
- Help message: *The weight of the component in grams.*
{{% /expand %}}

**Dimensions:** The dimensios of the component (height, width and
length). Can be left empty.
{{% expand title="**Details**" %}}
- Nested
- One
- Not required
- Fields:
    * **Height:** 
        - Decimal
        - One
        - Not required
        - Override Label: Height (cm)
    * **Width:** 
        - Decimal
        - One
        - Not required
        - Override Label: Width (cm)
    * **Lenght:** 
        - Decimal
        - One
        - Not required
        - Override Label: Lenght (cm)
{{% /expand %}}

**Cost:** The cost of the component and a historical record. It
can only be set through a action called "Set Current Cost" that makes
sure to update the new cost and to save in the historical record the
old cost of the component.
{{% expand title="**Details**" %}}
- Nested
- One
- Not required
- Always visible, even if empty
- Fields:
    * **Current Cost:** 
        - Nested
        - One
        - Not required
        - Read only
        - Visible only the the internal *Cost* is not empty.
        - Help message: Prefer the action "Set Current Cost" to update
        this field. Use direct edition ONLY to fix mistakes.
        - Fields:
            * **Cost:** 
                - Mone
                - One
                - Not required
                - Read only
            * **Date:** The date the actual cost was defined
                - Date
                - One
                - Not required
                - Default value: current date
                - Read only
    * **Historical Costs:** 
        - Nested
        - Many
        - Not required
        - Read only
        - Fields:
            * **Cost:** 
                - Mone
                - One
                - Not required
                - Read only
            * **Date:** The date the actual cost was defined
                - Date
                - One
                - Not required
                - Default value: current date
                - Read only
{{% /expand %}}

**Status:** Whether or not Weed Me is actively working with this
component or if this component needs to have its configurations 
reviewed
> - ***Active***   -> Weed Me is currently working with this Component
> - ***Warning***  -> One or more of the relationships of this 
> component needs to be reviewed
> - ***Inactive*** -> Weed Me has decided to not work with this 
> component anymore, it's like eliminating it from the system

{{% expand title="**Details**" %}}
- Choice
- One
- Required
- Default value: "Active"
{{% /expand %}}

---

## Actions

**Set Current Cost:**

**Deactivate:**

**Activate:** {{% icon exclamation-triangle %}} Not implemented


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
| Level | Read/Write |
| Class | Read/Write |
| Weight | Read/Write |
| Dimensions | Read/Write |
| Cost | Read Only |
| Status | Read Only |