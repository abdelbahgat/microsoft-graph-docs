---
title: "invitation resource type"
description: "Represents an invitation that is used to add external users to an organization."
ms.localizationpriority: medium
author: "Sammak"
ms.prod: "identity-and-sign-in"
doc_type: resourcePageType
---

# invitation resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Represents an invitation that is used to add external users to an organization. 

The invitation process uses the following flow:

* An invitation is created
* An invitation is sent to the invited user (containing an invitation link)
* The invited user clicks on the invitation link, signs in and redeems the invitation and creation of the user entity representing the invited user completes
* The user is redirected to a specific page after redemption completes

Creating an invitation will return a redemption URL in the response (*inviteRedeemUrl*). The create invitation API can automatically send an email containing the redemption URL to the invited user, by setting the *sendInvitationMessage* to true. You can also customize the message that will be sent to the invited user. Instead, if you wish to send the redemption URL through some other means, you can set the *sendInvitationMessage* to false and use the redeem URL from the response to craft your own communication. Currently, there is no API to perform the redemption process. The invited user has to click on the *inviteRedeemUrl* link sent in the communication in the step above, and go through the interactive redemption process in a browser. Once completed, the invited user becomes an external user in the organization.

>[!NOTE]
>The invitation status is tracked using the **externalUserState** and the **externalUserStateChangeDateTime** properties on the external [user](user.md) resource created as part of the invitation request.

## Methods
| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|[Create invitation](../api/invitation-post.md) | invitation | Write properties and relationships of invitation object.|

## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|invitedUserDisplayName|String|The display name of the user being invited.|
|invitedUserEmailAddress|String|The email address of the user being invited. Required. The following special characters are not permitted in the email address:<br><ul><li>Tilde (~)</li><li>Exclamation point (`!`)</li><li>At sign (`@`)</li><li>Number sign (`#`)</li><li>Dollar sign (`$`)</li><li>Percent (`%`)</li><li>Circumflex (`^`)</li><li>Ampersand (`&`)</li><li>Asterisk (`*`)</li><li>Parentheses (`( )`)</li><li>Hyphen (`-`)</li><li>Plus sign (`+`)</li><li>Equal sign (`=`)</li><li>Brackets (`[ ]`)</li><li>Braces (`{ }`)</li><li>Backslash (`\`)</li><li>Slash mark (`/`)</li><li>Pipe (`|`)</li><li>Semicolon (`;`)</li><li>Colon (`:`)</li><li>Quotation marks (`"`)</li><li>Angle brackets (`< >`)</li><li>Question mark (`?`)</li><li>Comma (`,`)</li></ul><br>However, the following exceptions apply:<br><ul><li>A period (`.`) or a hyphen (`-`) is permitted anywhere in the user name, except at the beginning or end of the name.</li><li>An underscore (`_`) is permitted anywhere in the user name. This includes at the beginning or end of the name.</li></ul>|
|invitedUserMessageInfo|[invitedUserMessageInfo](invitedusermessageinfo.md)|Additional configuration for the message being sent to the invited user, including customizing message text, language and cc recipient list.|
|inviteRedirectUrl|String|The URL user should be redirected to once the invitation is redeemed. Required.|
|inviteRedeemUrl|String|The URL the user can use to redeem their invitation. Read-only.|
|invitedUserType|String|The userType of the user being invited. By default, this is `Guest`. You can invite as `Member` if you're are company administrator. The default is `false`. |
|resetRedemption|Boolean|Reset the user's redemption status and reinvite a user while retaining their user identifier, group memberships, and app assignments. This property allows you to enable a user to sign-in using a different email address from the one in the previous invitation. For more information about using this property, see [Reset redemption status for a guest user (Preview)](/azure/active-directory/external-identities/reset-redemption-status#use-microsoft-graph-api-to-reset-redemption-status).|
|sendInvitationMessage|Boolean|Indicates whether an email should be sent to the user being invited. The default is `false`.|
|status|String|The status of the invitation. Possible values: `PendingAcceptance`, `Completed`, `InProgress`, and `Error`|

## Relationships
| Relationship | Type	|Description|
|:---------------|:--------|:----------|
|invitedUser|[user](user.md)|The user created as part of the invitation creation. Read-Only|

## JSON representation
Here is a JSON representation of the resource

<!-- 
{ 
    "blockType": "resource",
    "keyProperty":"id",
    "@odata.type": "microsoft.graph.invitation", 
    "optionalProperties": [
        "invitedUser"
     ],
    "baseType": "microsoft.graph.entity"
} 
-->
```json
{
  "id": "String",
  "invitedUserDisplayName": "String",
  "invitedUserEmailAddress": "String",
  "invitedUserMessageInfo": {"@odata.type": "microsoft.graph.invitedUserMessageInfo"},
  "sendInvitationMessage": false,
  "inviteRedirectUrl": "String",
  "inviteRedeemUrl": "String",
  "resetRedemption": false,
  "status": "String",
  "invitedUser": {"@odata.type": "microsoft.graph.user"},
  "invitedUserType": "String"
}
```


<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2016-22-25 14:57:30 UTC -->
<!--
{
  "type": "#page.annotation",
  "description": "invitation resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": []
}
-->


