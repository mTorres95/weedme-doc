+++
title = 'Unit Products'
date = 2024-01-07T21:34:34-03:00
draft = false
weight = 2
+++

This entity describes the repeated occurrence of 
**Atomic Products** in a presentation, specifying the packaging 
component information (type, size, and weight) at the unit product
level.

An example of a Unit Product would be a *Black Mountain Side 0.5g 
Pre-Roll (3 Pre-Rolls in a CR 116 mm Tube)*

The view for the records of this entity is under **PRODUCTS MASTER** 
**DATA > Products > Unit Products**

---

## Fields

**Name:** A human friendly way of recognizing a product   
{{% expand title="**Details**" %}}
- Text
- One
- Required
{{% /expand %}}

**Atomic Product:**  Composes the Unit Product, the dropdown shows
only the `active` atomic products.
{{% expand title="**Details**" %}}
- Relationship to PMD > Products > Atomic Products
- Sorted by "Label"
- Filtered by `status of Atomic Product == active`
- One
- Required if `status of Unit Product == active`
- Link enabled
{{% /expand %}}
    
**Quantity:** How many Atomic Products are encapsulated in this Unit
Product.

{{% expand title="**Details**" %}}
- Integer
- One
- Required `Atomic Product notEmpty`
{{% /expand %}}

**GTIN:** Relationship to the GTINs records. Allows to relate the 
unit GTINs to the case GTINs. If a GTIN is used by one Unit Product, 
it cannot be reused by another.

{{% expand title="**Details**" %}}
- Relationship to PMD > GTINs
- Sorted by "Label"
- Unique
- One
- Required
{{% /expand %}}

**Status:** Whether or not Weed Me is actively working with this
product or if this product needs to have its configurations reviewed
> - ***Active***   -> Weed Me is currently working with this Unit 
> Product
> - ***Warning***  -> One or more of the relationships of this 
> product needs to be reviewed
> - ***Inactive*** -> Weed Me has decided to not work with this 
> product anymore, it's like eliminating it from the system

{{% expand title="**Details**" %}}
- Choice
- One
- Required
- Default value: "Active"
{{% /expand %}}

**Components:** All the material components that form the product, 
composed by **Component** (a relationship to the component record) 
and **Quantity** (how many of each component does the product have).   
For Unit Products, this is required, since we need to specify how 
we're encapsulating the Atomic Products.
{{% expand title="**Details**" %}}
- Nested
- Manu
- Required
- Fields: 
    * **Component:** 
        - Relationship to PMD > Components
        - Sorted by "Label"
        - Filtered by `level == "Unit Product"` & `status == active`
        - Link enabled
        - One
        - Required
    * **Quantity:**
        - Integer
        - One
        - Required
        - Default value: 1
{{% /expand %}}

**Warning Message:** A message explaning why a product is in 
`warning` status
{{% expand title="**Details**" %}}
    - Long Text
    - One
    - Required if `status == warning`
    - Read only
    - Visible if not empty
{{% /expand %}}


---

## Permissions

| Entity | Admins |
| --- | --- |
| Create | Always |
| Access | Always |
| Edit | `status != inactive` |
| Delete | Never => `Make inactive instead` |
| History access | Always |
| Import | {{% icon icon="check" %}} |
| Eport | {{% icon icon="check" %}} |


| Field | Admins |
| --- | --- |
| Name | Read/Write |
| Atomic Product | Read/Write |
| Quantity | Read/Write |
| GTIN | Read/Write |
| Status | Read Only |
| Components | Read/Write |
| Warning message | Read only |
