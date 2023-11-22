---
title: "passwordProfile resource type"
description: "Contains the password profile associated with a user. The **passwordProfile** property of the user entity is a **passwordProfile** object."
ms.localizationpriority: medium
doc_type: resourcePageType
ms.prod: "users"
author: "yyuank"
---

# passwordProfile resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Contains the password profile associated with a user. The **passwordProfile** property of the [user](user.md) entity is a **passwordProfile** object. See an example to [Update the passwordProfile of a user](../api/user-update.md#example-3-update-the-passwordprofile-of-a-user-to-reset-their-password).


## Properties
| Property       | Type    |Description|
|:---------------|:--------|:----------|
|forceChangePasswordNextSignIn|Boolean|  `true` if the user must change her password on the next login; otherwise `false`. If not set, default is `false`. |
|forceChangePasswordNextSignInWithMfa|Boolean| If `true`, at next sign-in, the user must perform a multi-factor authentication (MFA) before being forced to change their password. The behavior is identical to **forceChangePasswordNextSignIn** except that the user is required to first perform a multi-factor authentication before password change. After a password change, this property will be automatically reset to `false`. If not set, default is `false`. |
|password|String|The password for the user. This property is required when a user is created. It can be updated, but the user will be required to change the password on the next login. The password must satisfy minimum requirements as specified by the user's **passwordPolicies** property. By default, a strong password is required.|

## JSON representation

Here is a JSON representation of the resource

<!-- {
  "blockType": "resource",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.passwordProfile"
}-->

```json
{
  "forceChangePasswordNextSignIn": true,
  "forceChangePasswordNextSignInWithMfa": false,
  "password": "string"
}

```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!--
{
  "type": "#page.annotation",
  "description": "passwordProfile resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": []
}
-->


