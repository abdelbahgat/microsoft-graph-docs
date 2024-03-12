---
title: "Update authenticationCombinationConfiguration"
description: "Update the properties of an authenticationCombinationConfiguration object."
author: "InbarckMS"
ms.localizationpriority: medium
ms.prod: "identity-and-sign-in"
doc_type: apiPageType
---

# Update authenticationCombinationConfiguration
Namespace: microsoft.graph

Update the properties of an [authenticationCombinationConfiguration](../resources/authenticationcombinationconfiguration.md) object. In use, only [fido2combinationConfigurations](../resources/fido2combinationconfiguration.md) may be updated as they are the only type of [authenticationCombinationConfiguration](../resources/authenticationcombinationconfiguration.md) that may be created.

## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type|Permissions (from least to most privileged)|
|:---|:---|
|Delegated (work or school account)|Policy.ReadWrite.ConditionalAccess, Policy.ReadWrite.AuthenticationMethod|
|Delegated (personal Microsoft account)|Not supported.|
|Application|Policy.ReadWrite.ConditionalAccess, Policy.ReadWrite.AuthenticationMethod|

[!INCLUDE [rbac-authenticationstrength-apis-write](../includes/rbac-for-apis/rbac-authenticationstrength-apis-write.md)]

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
PATCH /identity/conditionalAccess/authenticationStrength/policies/{authenticationStrengthPolicyId}/combinationConfigurations/{authenticationCombinationConfigurationId}
```

## Request headers
|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|
|Content-Type|application/json. Required.|

## Request body
[!INCLUDE [table-intro](../../includes/update-property-table-intro.md)]


|Property|Type|Description|
|:---|:---|:---|
|appliesToCombinations|authenticationMethodModes collection|The combinations to which this configuration applies. The only possible value for fido2combinationConfigurations is `fido2`. Required.|



## Response

If successful, this method returns a `204 No Content` response code.
## Examples

### Request
The following is an example of a request.

<!-- {
  "blockType": "request",
  "name": "update_authenticationcombinationconfiguration"
}
-->
``` http
PATCH https://graph.microsoft.com/v1.0/identity/conditionalAccess/authenticationStrength/policies/0e371351-6419-4c8a-8047-61eef0212ffb/combinationConfigurations/4643f174-fe85-42b8-8b84-516775750a30
Content-Type: application/json
Content-length: 130

{
  "appliesToCombinations": ["fido2"]
}
```

### Response
The following is an example of the response
<!-- {
  "blockType": "response",
  "truncated": true,
}
-->
``` http
HTTP/1.1 204 No Content
```

