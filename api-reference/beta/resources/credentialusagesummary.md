---
title: "credentialUsageSummary resource type"
description: "Represents the current state of how many users in your organization are using self-service password reset capabilities."
ms.localizationpriority: medium
author: "besiler"
ms.prod: "identity-and-access-reports"
doc_type: "resourcePageType"
---

# credentialUsageSummary resource type (deprecated)

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]
> [!CAUTION] 
  > The credential usage summary API is deprecated and will stop returning data on April 25, 2024. Please use the new [User registration details](https://learn.microsoft.com/en-us/graph/api/resources/userregistrationdetails?view=graph-rest-beta) API

Represents the current state of how many users in your organization are using self-service password reset capabilities.

## Methods

| Method       | Return Type | Description |
|:-------------|:------------|:------------|
| [getCredentialUsageSummary](../api/reportroot-getcredentialusagesummary.md) | credentialUsageSummary | Read properties and relationships of a credentialUsageSummary object. |

## Properties

| Property     | Type        | Description |
|:-------------|:------------|:------------|
| authMethod | usageAuthMethod | Represents the authentication method that the user used. Possible values are:`email`, `mobileSMS`, `mobileCall`, `officePhone`, `securityQuestion` (only used for self-service password reset), `appNotification`, `appCode`, `alternateMobileCall` (supported only in registration), `fido`, `appPassword`, `unknownFutureValue`. |
| failureActivityCount | Int64 | Provides the count of failed resets or registration data. |
| feature | featureType | Defines the feature to report. Possible values are: `registration`, `reset`, `unknownFutureValue`. |
| id | String | The unique identifier for the activity. Read-only. |
| successfulActivityCount | Int64 | Provides the count of successful registrations or resets. |

## Relationships

None.

## JSON representation

The following is a JSON representation of the resource.

<!-- {
  "blockType": "resource",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.credentialUsageSummary",
  "keyProperty": "id"
}-->

```json
{
  "id" : "String",
  "feature":"string",
  "successfulActivityCount":"Int64",
  "failureActivityCount": "Int64",
  "authMethod": "string"
}
```

<!-- uuid: 16cd6b66-4b1a-43a1-adaf-3a886856ed98
2019-02-04 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "credentialUsageSummary resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->

