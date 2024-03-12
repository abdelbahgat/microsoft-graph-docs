---
title: "authenticationMethodsRegistrationCampaign resource type"
description: "Represents the settings used to run campaigns to push users to set up targeted authentication methods."
author: "mjsantani"
ms.localizationpriority: medium
ms.prod: "identity-and-sign-in"
doc_type: resourcePageType
---

# authenticationMethodsRegistrationCampaign resource type

Namespace: microsoft.graph

Represents the settings used to run campaigns to push users to set up targeted authentication methods. Users are prompted to set up the authentication method after they successfully complete a MFA challenge. Only available for the Microsoft Authenticator app for MFA.

## Properties
|Property|Type|Description|
|:---|:---|:---|
|excludeTargets|[excludeTarget](../resources/excludetarget.md) collection|Users and groups of users that are excluded from being prompted to set up the authentication method.|
|includeTargets|[authenticationMethodsRegistrationCampaignIncludeTarget](../resources/authenticationmethodsregistrationcampaignincludetarget.md) collection|Users and groups of users that are prompted to set up the authentication method.|
|snoozeDurationInDays|Int32|Specifies the number of days that the user sees a prompt again if they select "Not now" and snoozes the prompt. Minimum: 0 days. Maximum: 14 days. If the value is "0", the user is prompted during every MFA attempt.|
|state|advancedConfigState|Enable or disable the feature. Possible values are: `default`, `enabled`, `disabled`, `unknownFutureValue`. The `default` value is used when the configuration hasn't been explicitly set and uses the default behavior of Azure Active Directory for the setting. The default value is `disabled`.|

## Relationships
None.

## JSON representation
The following is a JSON representation of the resource.
<!-- {
  "blockType": "resource",
  "@odata.type": "microsoft.graph.authenticationMethodsRegistrationCampaign"
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.authenticationMethodsRegistrationCampaign",
  "excludeTargets": [
    {
      "@odata.type": "microsoft.graph.excludeTarget"
    }
  ],
  "includeTargets": [
    {
      "@odata.type": "microsoft.graph.authenticationMethodsRegistrationCampaignIncludeTarget"
    }
  ],
  "snoozeDurationInDays": "Int32",
  "state": "String"
}
```
