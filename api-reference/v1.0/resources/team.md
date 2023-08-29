---
title: "team resource type"
description: "A Microsoft Teams team is a collection of channels. "
author: "AkJo"
ms.localizationpriority: high
ms.prod: "microsoft-teams"
doc_type: resourcePageType
---

# team resource type

Namespace: microsoft.graph

A team in Microsoft Teams is a collection of [channel](channel.md) objects.
A channel represents a topic, and therefore a logical isolation of discussion, within a team.

Every team is associated with a [Microsoft 365 group](../resources/group.md).
The group has the same ID as the team - for example, `/groups/{id}/team` is the same as `/teams/{id}`.
For more information about working with groups and members in teams, see [Use the Microsoft Graph REST API to work with Microsoft Teams](teams-api-overview.md).

## Methods

| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|[Create team](../api/team-post.md) | [teamsAsyncOperation](teamsasyncoperation.md) | Create a team from scratch. |
|[Create team from group](../api/team-put-teams.md) | [team](team.md) | Create a new team, or add a team to an existing Microsoft 365 group.|
|[Get team](../api/team-get.md) | [team](team.md) | Retrieve the properties and relationships of the specified team.|
|[Update team](../api/team-update.md) | [team](team.md) |Update the properties of the specified team. |
|[Delete team](../api/group-delete.md) | None |Delete the team and its associated group. |
|[List members](../api/team-list-members.md)|[conversationMember](../resources/conversationmember.md) collection|Get the list of members in the team.|
|[Add member](../api/team-post-members.md)|[conversationMember](../resources/conversationmember.md)|Add a new member to the team.|
|[Add members in bulk](../api/conversationmembers-add.md)|[actionResultPart](../resources/actionresultpart.md) collection|Add multiple members to the team in a single request.|
|[Get member](../api/team-get-members.md) | [conversationMember](conversationmember.md) collection | Get a member in the team.|
|[Update member's role](../api/team-update-members.md)|[conversationMember](../resources/conversationmember.md)|Change a member to an owner or back to a regular member.|
|[Remove member](../api/team-delete-members.md)|None|Remove an existing member from the team.|
|[Archive team](../api/team-archive.md) | [teamsAsyncOperation](../resources/teamsasyncoperation.md) |Put the team in a read-only state. |
|[Unarchive team](../api/team-unarchive.md) | [teamsAsyncOperation](../resources/teamsasyncoperation.md) |Restore the team to a read-write state. |
|[Clone team](../api/team-clone.md) | [teamsAsyncOperation](../resources/teamsasyncoperation.md) |Copy the team and its associated group. |
|[List your teams](../api/user-list-joinedteams.md) | [team](team.md) collection | List the teams you are a member of. |
|[List associated teams](../api/associatedteaminfo-list.md) | [associatedTeamInfo](associatedteaminfo.md) collection | Get the list of [teams](../resources/associatedteaminfo.md) in Microsoft Teams that a [user](../resources/user.md) is associated with. |
|[Complete migration](../api/team-completemigration.md)|[team](team.md)| Removes migration mode from the team and makes the team available to users to post and read messages.|
|[List all channels](../api/team-list-allchannels.md)|[channel](../resources/channel.md) collection|Get the list of [channels](../resources/channel.md) either in this [team](../resources/team.md) or shared with this [team](../resources/team.md) (incoming channels).|
|[List channels](../api/channel-list.md)|[channel](../resources/channel.md) collection|Get the list of [channels](../resources/channel.md) in a **team**.|
|[List incoming channels](../api/team-list-incomingchannels.md)|[channel](../resources/channel.md) collection|Get the list of incoming [channels](../resources/channel.md) (channels shared with a [team](../resources/team.md)).|
|[Remove incoming channel](../api/team-delete-incomingchannels.md) | None| Remove an incoming [channel](../resources/channel.md) (a **channel** shared with a **team**) from a [team](../resources/team.md).|
|[List apps installed in team](../api/team-list-installedapps.md) | [teamsAppInstallation](teamsappinstallation.md) collection | List apps installed in a team.|
|[Add app to team](../api/team-post-installedapps.md) |None | Add (install) an app to a team.|
|[Get app installed in team](../api/team-get-installedapps.md) | [teamsAppInstallation](teamsappinstallation.md) | Get the specified app installed in a team.|
|[Upgrade app installed in team](../api/team-teamsappinstallation-upgrade.md) | None | Upgrade the app installed in a team to the latest version.|
|[Remove app from team](../api/team-delete-installedapps.md) | None | Remove (uninstall) an app from a team.|

## Properties

| Property | Type | Description |
|:---------------|:--------|:----------|
|displayName|string| The name of the team. |
|description|string| An optional description for the team. Maximum length: 1024 characters. |
|classification|string| An optional label. Typically describes the data or business sensitivity of the team. Must match one of a pre-configured set in the tenant's directory. |
|specialization|[teamSpecialization](teamspecialization.md)| Optional. Indicates whether the team is intended for a particular use case.  Each team specialization has access to unique behaviors and experiences targeted to its use case. |
|visibility|[teamVisibilityType](teamvisibilitytype.md)| The visibility of the group and team. Defaults to Public. |
|funSettings|[teamFunSettings](teamfunsettings.md) |Settings to configure use of Giphy, memes, and stickers in the team.|
|guestSettings|[teamGuestSettings](teamguestsettings.md) |Settings to configure whether guests can create, update, or delete channels in the team.|
|internalId | string | A unique ID for the team that has been used in a few places such as the audit log/[Office 365 Management Activity API](/office/office-365-management-api/office-365-management-activity-api-reference). |
|isArchived|Boolean|Whether this team is in read-only mode. |
|memberSettings|[teamMemberSettings](teammembersettings.md) |Settings to configure whether members can perform certain actions, for example, create channels and add bots, in the team.|
|messagingSettings|[teamMessagingSettings](teammessagingsettings.md) |Settings to configure messaging and mentions in the team.|
|webUrl|string (readonly) | A hyperlink that will go to the team in the Microsoft Teams client. This is the URL that you get when you right-click a team in the Microsoft Teams client and select **Get link to team**. This URL should be treated as an opaque blob, and not parsed. |
|createdDateTime|dateTimeOffset|Timestamp at which the team was created.|
|tenantId |string | The ID of the Azure Active Directory tenant. |

### Instance attributes

Instance attributes are properties with special behaviors. These properties are temporary and either a) define behavior the service should perform or b) provide short-term property values, like a download URL for an item that expires.

| Property name| Type   | Description
|:-----------------------|:-------|:-------------------------|
|@microsoft.graph.teamCreationMode|string|Indicates that the team is in migration state and is currently being used for migration purposes. It accepts one value: `migration`. **Note**: In the future, Microsoft may require you or your customers to pay additional fees based on the amount of data imported.|

For a POST request example, see [Request (create team in migration state)](/microsoftteams/platform/graph-api/import-messages/import-external-messages-to-teams).

## Relationships

| Relationship | Type | Description |
|:---------------|:--------|:----------|
|allChannels|[channel](channel.md) collection|List of channels either hosted in or shared with the team (incoming channels).|
|channels|[channel](channel.md) collection|The collection of channels and messages associated with the team.|
|incomingChannels|[channel](channel.md) collection|List of [channels](../resources/channel.md) shared with the team.|
|installedApps|[teamsAppInstallation](teamsappinstallation.md) collection|The apps installed in this team.|
|members|[conversationMember](../resources/conversationmember.md) collection|Members and owners of the team.|
|operations|[teamsAsyncOperation](teamsasyncoperation.md) collection| The async operations that ran or are running on this team. |
|[primaryChannel](../api/team-get-primarychannel.md)|[channel](channel.md)| The general channel for the team. |
|schedule|[schedule](schedule.md)| The schedule of shifts for this team.|
|photo|[profilePhoto](../resources/profilephoto.md)| The profile photo for the team. |
|template|[teamsTemplate](teamstemplate.md)| The template this team was created from. See [available templates](/MicrosoftTeams/get-started-with-teams-templates). |

## JSON representation

The following is a JSON representation of the resource.

>**Note:** If the team is of type class, a **classSettings** property is applied on the team.

<!-- {
  "blockType": "resource",
  "@odata.type": "microsoft.graph.team",
  "baseType": "microsoft.graph.entity"
}-->

```json
{
  "guestSettings": {"@odata.type": "microsoft.graph.teamGuestSettings"},
  "memberSettings": {"@odata.type": "microsoft.graph.teamMemberSettings"},
  "messagingSettings": {"@odata.type": "microsoft.graph.teamMessagingSettings"},
  "funSettings": {"@odata.type": "microsoft.graph.teamFunSettings"},
  "internalId": "string",
  "isArchived": false,
  "webUrl": "string (URL)",
  "classSettings": {"@odata.type": "microsoft.graph.teamClassSettings"},
  "createdDateTime": "dateTimeOffset"
}
```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "team resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->

## See also

- [Use the Microsoft Graph API to work with Microsoft Teams](teams-api-overview.md)
- [Creating a group with a team](/graph/teams-create-group-and-team)
- [List all teams](/graph/teams-list-all-teams)
