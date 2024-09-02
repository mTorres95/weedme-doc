+++
title = 'Case Products'
date = 2024-01-07T21:41:48-03:00
draft = false
weight = 3
+++

Represents the finished products **Weed Me** sells to their customers.
Combines General Information, Case Information, Brand, Customer and
Costs information.

An example of a Case Product would be a *Case of 24 - Black Mountain*
*Side 0.5g Pre-Rolls (3 Pre-rolls in a CR 116 mm Tube) 1.5g in total*

The view for the records of this entity is under **PRODUCTS MASTER DATA**
**> Products > Case Products**

---

## Fields

**General Information:** Gathers the **Description** (representing the 
name of the product) and the **Image**.
{{% expand title="**Details**" %}}
- Nested
- One
- Not required
- Fields:
    * **Description:**
        - Text
        - One
        - Description: This is also called “internal name” within the
        framework, it includes a description of the product and it is 
        used to identify the product in all the tables.
        - Required
    * **Image:**
        - File
        - One
        - Description: An image of the final product
        - Not required
{{% /expand %}}

**Case Information:** The information regarding the componsition of 
the case product, including **Unit Product** and the **Quantity** of 
them packed in the Case Product, the **Components** of the packaging, 
the estimated **Cases on Skid** and ****.
{{% expand title="**Details**" %}}
- Nested
- One
- Not required
- Fields:
    * **Unit Product:**
        - Relationship to PMD > Products > Unit Products
        - Filtered by `status == active`
        - One
        - Description: Relationship to the Unit Product record that 
        composes the Finished Product
        - Required if `status == active`
        - Link enabled - Allowed to edit
        - Sorted by "Label"
    * **Quantity:**
        - Quantity
        - One
        - Description: This is the amount of unit products included on
        the product also called units per case
        - Required if `case information > unit product not empty` 
    * **Components:**
        - Nested
        - Many
        - Required if `status == active`
        - Fields:
            * **Component:**
                - Relationship to PMD > Components
                - Filtered by `level == case product` & `status == active`
                - One
                - Required
                - Link enabled - Allowed to edit
                - Sorted by "Label"
            * **Quantity:**
                - Integer
                - One
                - Required
    * **Cases on Skid:**
        - Integer
        - One
        - Required
    * **-:**
{{% /expand %}}

**Brand:** The brand that identifies the product.
{{% expand title="**Details**" %}}
- Relationship to PMD > Brands
- One
- Not required
- Sorted by "Label"
{{% /expand %}}

**Customers:** The list of independent **Customers** to whom **Weed**
**Me** sells the Case Product, the **SKU** identifier of the product 
for the customer and the **Price** it's sold to them.
{{% expand title="**Details**" %}}
- Nested
- Many
- Not required
- Fields:
    * **Customer:**
        - Relationship to CRM > Customers
        - Filtered by `board is empty`
        - One
        - Required
        - Sorted by "Label"
    * **SKU:**
        - Text
        - One
        - Not required
    * **Price:**
{{% /expand %}}

**GTIN:** Case GTINs, they are dependant of the Unit Product GTIN as 
part of the GS1 registration process.
{{% expand title="**Details**" %}}
- Dynamic choice
- One
- Required if `status == active`
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

## Actions

**Deactivate:**

**Duplicate:**

**Activate:**

---

## Permissions

| Entity | Admins |
| --- | --- |
| Create | Always |
| Access | Always |
| Edit | `status != inactive` |
| Delete | Never => `Make inactive instead` |
| Audit logs | Always |
| Import | {{% icon icon="check" %}} |
| Eport | {{% icon icon="check" %}} |

| Field | Admins |
| --- | --- |
| General Information | Read/Write |
| Case Information | Read/Write |
| Brand | Read/Write |
| Customers | Read/Write |
| GTIN | Read/Write |
| Status | Read Only |
| Warning Message | Read Only |