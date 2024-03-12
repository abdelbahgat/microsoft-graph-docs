---
title: "authenticationStrengthPolicy: updateAllowedCombinations"
description: "Update the allowedCombinations collection for a given authentication strength policy object."
author: "InbarckMS"
ms.localizationpriority: medium
ms.prod: "identity-and-sign-in"
doc_type: apiPageType
---

# authenticationStrengthPolicy: updateAllowedCombinations
Namespace: microsoft.graph

Update the allowedCombinations property of an [authenticationStrengthPolicy](../resources/authenticationstrengthpolicy.md) object. To update other properties of an authenticationStrengthPolicy object, use the [Update authenticationStrengthPolicy](authenticationstrengthpolicy-update.md) method.

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
POST /policies/authenticationStrengthPolicies/{authenticationStrengthPolicyId}/updateAllowedCombinations
```

## Request headers
|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|
|Content-Type|application/json. Required.|

## Request body
In the request body, supply a JSON representation of the parameters.

The following table shows the parameters that can be used with this action.

|Parameter|Type|Description|
|:---|:---|:---|
|allowedCombinations|authenticationMethodModes collection|The authentication method combinations allowed by this authentication strength policy. The possible values of this flagged enum are: `password`, `voice`, `hardwareOath`, `softwareOath`, `sms`, `fido2`, `windowsHelloForBusiness`, `microsoftAuthenticatorPush`, `deviceBasedPush`, `temporaryAccessPassOneTime`, `temporaryAccessPassMultiUse`, `email`, `x509CertificateSingleFactor`, `x509CertificateMultiFactor`, `federatedSingleFactor`, `federatedMultiFactor`, `unknownFutureValue`. For the list of allowed combinations, call the [List authenticationMethodModes](../api/authenticationstrengthroot-list-authenticationmethodmodes.md) API. Required.|

## Response

If successful, this action returns a `200 OK` response code and a [updateAllowedCombinationsResult](../resources/updateallowedcombinationsresult.md) in the response body.

## Examples

### Request
The following is an example of a request.
<!-- {
  "blockType": "request",
  "name": "authenticationstrengthpolicythis.updateallowedcombinations"
}
-->
``` http
POST https://graph.microsoft.com/v1.0/policies/authenticationStrengthPolicies/33c5d2c0-884e-4b5d-a5b8-5395082b092c/updateAllowedCombinations
Content-Type: application/json
Content-length: 51

{
  "allowedCombinations": [
      "password, voice"
  ]
}
```

### Response
The following is an example of the response
>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.updateAllowedCombinationsResult"
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "@odata.type" : "#microsoft.graph.updateAllowedCombinationsResult",
  "previousCombinations": [
    "fido2",
    "password, voice"
  ],
  "currentCombinations": [
    "password, voice"
  ],
  "conditionalAccessReferences": [
    "53a3968a-ae2c-4b82-a313-091d10c52bfa"
  ],
  "additionalInformation": "You have lowered the security of the My Custom Strength authentication strength by adding a lower security combination. This Authentication Strength is referenced by one or more Conditional Access policies. Review conditionalAccessReferences to understand which Conditional Access policies were impacted by this change. To reverse your changes back, use updateAllowedCombinations action with the previousCombinations values."
}
```

