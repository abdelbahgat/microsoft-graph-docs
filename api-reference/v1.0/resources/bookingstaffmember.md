---
title: "bookingStaffMember resource type"
description: "Represents a staff member who provides services in a bookingBusiness."
ms.localizationpriority: medium
author: "arvindmicrosoft"
ms.prod: "bookings"
doc_type: resourcePageType
---

# bookingStaffMember resource type

Namespace: microsoft.graph

Represents a staff member who provides services in a [bookingBusiness](bookingbusiness.md). 

Staff members can be part of the Microsoft 365 tenant where the **booking business** is configured, or they can use email services from other email providers.

When booking appointments, the Bookings API considers the following settings to determine a staff member's availability: 

1. By default, the hours of operation of the business (the **businessHours** property of the [bookingBusiness](bookingbusiness.md) entity) represents the general availability of the staff member.
2. If **useBusinessHours** is false, then the staff member's specific work hours (**workingHours** property of the **bookingStaffmember** entity) represents that member's general availability.
3. If **availabilityIsAffectedByPersonalCalendar** is true, then the Bookings API would first look at the staff member's generally available hours (as determined by either #1 or #2), and verify availability during those hours in the staff member's personal calendar, before making a booking.

Inherits from [bookingStaffMemberBase](bookingstaffmemberbase.md).

Microsoft Bookings supports a maximum of 100 staff members in a booking calendar.

## Methods

| Method		   | Return Type	|Description|
|:---------------|:--------|:----------|
|[List staff members](../api/bookingbusiness-list-staffmembers.md) | [bookingStaffMember](bookingstaffmember.md) collection | Get a list of **bookingStaffMember** objects in the specified [bookingbusiness](../resources/bookingbusiness.md). |
|[Create bookingStaff](../api/bookingbusiness-post-staffmembers.md) | [bookingStaffMember](bookingstaffmember.md) collection | Create a new **bookingStaffMember** in the specified [bookingbusiness](../resources/bookingbusiness.md). |
|[Get bookingStaffMember](../api/bookingstaffmember-get.md) | [bookingStaffMember](bookingstaffmember.md) |Get the properties and relationships of a **bookingStaffMember** in the specified [bookingbusiness](../resources/bookingbusiness.md).|
|[Update](../api/bookingstaffmember-update.md) | [bookingStaffMember](bookingstaffmember.md)	|Update the properties of a **bookingStaffMember** in the specified [bookingbusiness](../resources/bookingbusiness.md).|
|[Delete](../api/bookingstaffmember-delete.md) | None |Delete a staff member in the specified [bookingbusiness](../resources/bookingbusiness.md). |

## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|availabilityIsAffectedByPersonalCalendar|Boolean|True means that if the staff member is a Microsoft 365 user, the Bookings API would verify the staff member's availability in their personal calendar in Microsoft 365, before making a booking. |
|displayName|String|The name of the staff member, as displayed to customers. Required.|
|emailAddress|String|The email address of the staff member. This can be in the same Microsoft 365 tenant as the business, or in a different email domain. This email address can be used if the **sendConfirmationsToOwner** property is set to true in the scheduling policy of the business. Required.|
|id|String| The ID of the staff member, in a GUID format. Read-only.|
|role|bookingStaffRole| The role of the staff member in the business. Possible values are: `guest`, `administrator`, `viewer`, `externalGuest` and `unknownFutureValue`. Required.|
|timeZone|String|The time zone of the staff member. For a list of possible values, see [dateTimeTimeZone](datetimetimezone.md).|
|useBusinessHours|Boolean|True means the staff member's availability is as specified in the **businessHours** property of the business. False means the availability is determined by the staff member's **workingHours** property setting.|
|workingHours|[bookingWorkHours](bookingworkhours.md) collection|The range of hours each day of the week that the staff member is available for booking. By default, they are initialized to be the same as the **businessHours** property of the business.|

## Relationships
None


## JSON representation

The following is a JSON representation of the resource.

<!-- {
  "blockType": "resource",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.bookingStaffMember",
  "baseType": "microsoft.graph.bookingStaffMemberBase"
}-->

```json
{
  "availabilityIsAffectedByPersonalCalendar": true,
  "displayName": "String",
  "emailAddress": "String",
  "id": "String (identifier)",
  "role": {"@odata.type": "microsoft.graph.bookingStaffRole"},
  "useBusinessHours": true,
  "workingHours": [{"@odata.type": "microsoft.graph.bookingWorkHours"}],
  "timeZone": "String"
}

```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!--
{
  "type": "#page.annotation",
  "description": "bookingStaffMember resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": []
}
-->


