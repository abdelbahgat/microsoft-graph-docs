---
title: "teamsAppInstallation resource type"
description: "A teamsApp installed in a team, a chat, or a user's personal scope. "
author: "AkJo"
ms.localizationpriority: medium
ms.prod: "microsoft-teams"
doc_type: resourcePageType
---

# teamsAppInstallation resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

A [teamsApp](teamsapp.md) installed in a [team](team.md), a [chat](chat.md), or the personal scope of a [user](user.md). Any bots that are part of the app will become part of any team, chat, or user's personal scope that the app is added to.

> [!NOTE]
> The `id` of a **teamsAppInstallation** resource is not the same value as the `id` of the associated **teamsApp** resource.

## Methods

| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|[List apps installed in team](../api/team-list-installedapps.md) | [teamsAppInstallation](teamsappinstallation.md) collection | List apps installed in a team.|
|[Get app installed in team](../api/team-get-installedapps.md) | [teamsAppInstallation](teamsappinstallation.md) | Get the specified app installed in a team.|
|[Add app to team](../api/team-post-installedapps.md) |None | Add (install) an app to a team.|
|[Upgrade app installed in team](../api/team-teamsappinstallation-upgrade.md) | None | Upgrade the app installed in a team to the latest version.|
|[Remove app from team](../api/team-delete-installedapps.md) | None | Remove (uninstall) an app from a team.|
|[List apps installed for user](../api/userteamwork-list-installedapps.md) | [userScopeTeamsAppInstallation](userscopeteamsappinstallation.md) collection | List apps installed in the personal scope of a user.|
|[Get app installed for user](../api/userteamwork-get-installedapps.md)| [userScopeTeamsAppInstallation](userscopeteamsappinstallation.md) | Get the specified app installed in the personal scope of a user. |
|[Add app for user](../api/userteamwork-post-installedapps.md) | | Add (install) an app in the personal scope of a user.|
|[Upgrade app installed for user](../api/userteamwork-teamsappinstallation-upgrade.md) | None | Upgrade the app installed in the personal scope of a user to the latest version.|
|[Remove app for user](../api/userteamwork-delete-installedapps.md) | None | Remove (uninstall) an app in the personal scope of a user.|
|[List apps in chat](../api/chat-list-installedapps.md) |[teamsAppInstallation](teamsappinstallation.md) collection | List apps installed in a chat.|
|[Get app installed in chat](../api/chat-get-installedapps.md) | [teamsAppInstallation](teamsappinstallation.md) | Get the specified app installed in a chat.|
|[Add app in chat](../api/chat-post-installedapps.md) | | Add (install) an app to a chat.|
|[Upgrade app in chat](../api/chat-teamsappinstallation-upgrade.md) | None | Upgrade the app installed in a chat to the latest version.|
|[Remove app from chat](../api/chat-delete-installedapps.md) | None | Remove (uninstall) app from a chat.|

## Properties

| Property            | Type     | Description |
|:------------------- |:-------- |:----------- |
| id                  | string   | A unique ID (not the team's app ID). |
|consentedPermissionSet|[teamsAppPermissionSet](../resources/teamsapppermissionset.md)|The set of resource-specific permissions consented to while installing or upgrading the teamsApp.|

## Relationships

| Relationship   | Type    | Description |
|:---------------|:--------|:----------|
|teamsApp|[teamsApp](teamsapp.md)| The app that is installed. |
|teamsAppDefinition|[teamsAppDefinition](teamsappdefinition.md)| The details of this version of the app. |

## JSON representation

The following is a JSON representation of the resource.

<!-- {
  "blockType": "resource",
  "@odata.type": "microsoft.graph.teamsAppInstallation",
  "baseType": "microsoft.graph.entity"
}-->

```json
{
  "id": "string",
  "consentedPermissionSet": "#microsoft.graph.teamsAppPermissionSet"
}
```

## See also

- [teamsApp](teamsapp.md)
- [teamsAppDefinition](teamsappdefinition.md)
- [teamsTab](../resources/teamstab.md)
- [userScopeTeamsAppInstallation](../resources/userscopeteamsappinstallation.md)
- [Teams app installation lifecycle C# sample](https://github.com/OfficeDev/Microsoft-Teams-Samples/blob/main/samples/graph-app-installation-lifecycle/csharp)
- [Teams app installation lifecycle Node.js sample](https://github.com/OfficeDev/Microsoft-Teams-Samples/blob/main/samples/graph-app-installation-lifecycle/nodejs)

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!--
{
  "type": "#page.annotation",
  "description": "teamsApp resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": []
}
-->


