+++
title = 'Atomic Products'
date = 2024-01-07T21:10:36-03:00
draft = false
weight = 1
+++

This entity represents the **smallest, indivisible part of the** 
**product**. It includes information about a specific type of product, 
such as a pre-roll, and its cannabis and material components.

An example of a Atomic Product would be a *Black Mountain Side Milled*
*Flower Pre-Roll 0.5g*

The view for the records of this entity is under **PRODUCTS MASTER**
**DATA > Products > Atomic Products**

---

## Fields

**Name:** A human friendly way of recognizing a product   
{{% expand title="**Details**" %}}
- Text
- One
- Required
{{% /expand %}}

**Product Type:**  List of all the product types applicable for Atomic Products
{{% expand title="**Details**" %}}
- Relationship to PMD > Atomic Product Types
- Sorted by "Label"
- One
- Required if status equals active
{{% /expand %}}
    
**Cannabis:** Representation of the cannabis component, composed by
**Profile** (specific variety or type of cannabis plant) and **Weight** (in grams)

{{% expand title="**Details**" %}}
- Nested
- One
- Required
- Fields: 
    * **Profile:** 
        - Relationship to PMD > Profiles
        - Sorted by "Label"
        - One
        - Required
    * **Weight:**
        - Decimal
        - One
        - Required
        - Override Label: "Weight (g)
        - Help message: "The weight of the component in grams"
{{% /expand %}}

**Status:** Whether or not Weed Me is actively working with this
product or if this product needs to have its configurations reviewed
> - ***Active***   -> Weed Me is currently working with this Atomic 
> Product
> - ***Warning***  -> One or more of the relationships of this 
> product needs to be reviewed
> - ***Inactive*** -> Weed ME has decided to not work with this 
> product anymore, it's like eliminating it from the system

{{% expand title="**Details**" %}}
- Choice
- One
- Required
- Default value: "Active"
{{% /expand %}}

**Components:** All the material components that form the product, 
composed by **Component** (a relationship to the component record) 
and **Quantity** (how many of each component does the product have) 
{{% expand title="**Details**" %}}
- Nested
- Manu
- Not required
- Fields: 
    * **Component:** 
        - Relationship to PMD > Components
        - Sorted by "Label"
        - Filtered by `level == "Atomic Product"` & `status == active`
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
| Product Type | Read/Write |
| Cannabis | Read/Write |
| Status | Read Only |
| Components | Read/Write |
| Warning message | Read only |

