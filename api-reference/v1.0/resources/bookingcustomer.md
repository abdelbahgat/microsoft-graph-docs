---
title: "bookingCustomer resource type"
description: "Represents a customer of a bookingBusiness."
ms.localizationpriority: medium
author: "arvindmicrosoft"
ms.prod: "bookings"
doc_type: resourcePageType
---

# bookingCustomer resource type

Namespace: microsoft.graph

Represents a customer of a [bookingBusiness](bookingbusiness.md).

Inherits from [bookingCustomerBase](bookingcustomerbase.md).

## Methods

| Method		   | Return Type	|Description|
|:---------------|:--------|:----------|
|[List customers](../api/bookingbusiness-list-customers.md) | [bookingCustomer](bookingcustomer.md) collection | Get a list of **bookingCustomer** objects. |
|[Create bookingCustomer](../api/bookingbusiness-post-customers.md) | [bookingCustomer](bookingcustomer.md) | Create a new **bookingCustomer** object. |
|[Get bookingCustomer](../api/bookingcustomer-get.md) | [bookingCustomer](bookingcustomer.md) |Read the properties and relationships of a **bookingCustomer** object.|
|[Update](../api/bookingcustomer-update.md) | [bookingCustomer](bookingcustomer.md)	|Update a **bookingCustomer** object. |
|[Delete](../api/bookingcustomer-delete.md) | None |Delete a **bookingCustomer** object. |

## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|displayName|String|The name of the customer.|
|emailAddress|String|The SMTP address of the customer.|
|id|String| The ID of the customer. Read-only.|
|addresses|[physicalAddress](../resources/physicaladdress.md) collection|Addresses associated with the customer. The attribute **type** of physicalAddress is not supported in v1.0. Internally we map the addresses to the type `others`.|
|phones|[phone](../resources/phone.md) collection|Phone numbers associated with the customer, including home, business and mobile numbers.|

## Relationships
None


## JSON representation

The following is a JSON representation of the resource.

<!-- {
  "blockType": "resource",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.bookingCustomer",
  "baseType": "microsoft.graph.bookingCustomerBase"
}-->

```json
{
  "displayName": "String",
  "emailAddress": "String",
  "id": "String (identifier)",
  "addresses": [
    {
      "@odata.type": "microsoft.graph.physicalAddress"
    }
  ],
  "phones": [
    {
      "@odata.type": "microsoft.graph.phone"
    }
  ]
}

```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!--
{
  "type": "#page.annotation",
  "description": "bookingCustomer resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": []
}
-->


