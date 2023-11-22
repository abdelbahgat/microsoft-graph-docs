---
title: "keyCredentialConfiguration resource type"
description: "Represents a key credential configuration object that contains properties to configure restrictions for application certificates."
ms.localizationpriority: medium
author: "madansr7"
ms.prod: "identity-and-sign-in"
doc_type: resourcePageType
---

# keyCredentialConfiguration resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Represents a key credential configuration object that contains properties to configure restrictions for application certificates.

## Properties

| Property                            | Type                                                                               | Description                                                                                                                                                                                                                                                                                   |
| :---------------------------------- | :--------------------------------------------------------------------------------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
|certificateBasedApplicationConfigurationIds|String collection|Collection of GUIDs that point to the [certificateBasedApplicationConfiguration](../resources/certificatebasedapplicationconfiguration.md) that contains the collection of allowed root and intermediate certificate authorities.|
| maxLifeTime                         | Duration                                                                           |Value that can be used as the maximum duration in days, hours, minutes, or seconds from the date of key creation, for which the key is valid.  Defined in ISO 8601 format for Durations. For example, `P4DT12H30M5S` represents a duration of four days, twelve hours, thirty minutes, and five seconds. This property is required when **restrictionType** is set to `keyLifetime`. |
| restrictForAppsCreatedAfterDateTime | DateTimeOffset                                                                     | Timestamp when the policy is enforced for all apps created on or after the specified date. For existing applications, the enforcement date would be back dated. To apply to all applications regardless of their creation date, this property would be `null`. Nullable. |
| restrictionType                     | appKeyCredentialRestrictionType | The type of restriction being applied. Possible values are `asymmetricKeyLifetime`, `unknownFutureValue`. Each value of restrictionType can be used only once per policy.                                                                                                                        |

## Relationships

None.

## JSON representation

The following is a JSON representation of the resource.

<!-- {
  "blockType": "resource",
  "@odata.type": "microsoft.graph.keyCredentialConfiguration"
}
-->

```json
{
  "@odata.type": "#microsoft.graph.keyCredentialConfiguration",
  "certificateBasedApplicationConfigurationIds": ["String"],
  "maxLifetime": "String (duration)",
  "restrictForAppsCreatedAfterDateTime": "String (timestamp)",
  "restrictionType": "String"
}
```
