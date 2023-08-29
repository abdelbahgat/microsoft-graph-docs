---
title: "Microsoft Teams API overview"
description: "Use the Microsoft Teams API in Microsoft Graph to automate team lifecycles, create and manage teams and channels, deploy apps, and get notified about changes."
author: "nkramer"
ms.localizationpriority: high
ms.prod: "microsoft-teams"
ms.custom: scenarios:getting-started
---

# Microsoft Teams API overview

[Microsoft Teams](https://products.office.com/microsoft-teams) is the ultimate hub for teamwork and intelligent communications. Built on the strength and scale of [Microsoft 365](https://products.office.com/) with over 120 million users, Microsoft Teams delivers chat-based collaboration, meetings, calling, and enterprise voice features.


> [!VIDEO https://www.youtube-nocookie.com/embed/KCvAhQEJmyY]


## Why integrate with Microsoft Teams?
The rich features of Microsoft Teams and its API open up many scenarios for app developers. The following sections list a few of them.

## Automate team lifecycles

Use Microsoft Graph to [create a new virtual team](/graph/api/team-put-teams) when a new business issue arises, 
[add the right people](/graph/api/group-post-members) to the team, 
and configure the team with 
[channels](/graph/api/channel-post),
[tabs](/graph/teams-configuring-builtin-tabs),
and [apps](/graph/api/team-post-installedapps).
If you want to get the new team together to discuss the business issue, 
[add a new event](/graph/api/group-post-events) to the team calendar.

![Automate team lifecycles by creating a team, adding members and owners, configuring team settings, adding channels, installing apps, adding tabs, and archiving or deleting the team when the time comes.](images/teams-lifecycle.png)

When the business issue is resolved and you no longer need the team, 
use the Microsoft Teams API to [archive](/graph/api/team-archive)
or [delete](/graph/api/group-delete) the team. 
If you know the maximum duration of the team when you create it, 
set an [Microsoft 365 group expiration policy](https://support.office.com/article/office-365-group-expiration-policy-8d253fe5-0e09-4b3c-8b5e-f48def064733?ui=en-US&rs=en-US&ad=US)
for the team that automatically removes the team according to the policy.

## Get work done even when no one is around

Use [application permissions](permissions-reference.md) to work with 
[teams](/graph/api/resources/team), [channels](/graph/api/resources/channel), and 
[tabs](/graph/api/resources/teamstab)
without human intervention. 
Create a new channel when your customer files an order.
Automatically create teams for classes at the beginning of the school year, and archive them at the end.

## Create teams linked to your app

Let customers create new [teams](/graph/api/resources/team) and [channels](/graph/api/resources/channel). 
[Install](/graph/api/teamsappinstallation-add) your 
[Teams app](/microsoftteams/platform/#pivot=home&panel=home-all) in the new teams. 
[Pin your app to a tab](/graph/api/teamstab-add) in the new channel. 
[Send messages](/graph/api/chatmessage-post) to the channel linking back to your website.

## Create and manage multiple teams and channels

Microsoft Graph makes it easy to create large numbers of teams and populate them with users and channels,
by automating the creation and management of [teams](/graph/api/resources/team), [channels](/graph/api/resources/channel),
[tabs](/graph/api/resources/teamstab), and [apps](/graph/api/resources/teamsapp).
Microsoft Graph also lets you [find](teams-list-all-teams.md) 
and [archive](/graph/api/team-archive)
the teams you are no longer using. 
This is the same API that the [Microsoft Teams Admin Center](/microsoftteams/enable-features-office-365)
and [Teams PowerShell cmdlets](/microsoftteams/teams-powershell-overview) are built on.

## Deploy apps to teams

[List the teams in your tenant](teams-list-all-teams.md), 
and [install apps](/graph/api/teamsappinstallation-add) to them. 
[Create tabs](/graph/api/teamstab-add) in channels to give users easy access to apps.

## Use Microsoft Graph in any kind of app

Microsoft Teams apps give work groups a new tool to make collaboration a more productive and compelling experience. These apps let work group users share assets, interact through chat, and schedule events on the team calendar. These apps can also automate creating teams, channels, and conversations, enhancing the value of Microsoft Teams.

You can create websites, services, and native platform applications that run outside the Microsoft Teams user experience, and call the Teams API to automate Teams scenarios.

### Types of apps enabled for Microsoft Teams

![Call the Microsoft Teams API from tabs, bots, websites, and services](images/teamsappendpoints.png)

These collaboration tools include Microsoft Graph-enabled tabs or bots running inside Microsoft Teams apps. You can also call Microsoft Graph outside of a Microsoft Teams app, such as from a website or a web service. If you've already enabled your website for Microsoft Graph, you can use that work for Microsoft Teams by using the [Microsoft Teams developer platform](/microsoftteams/platform/#pivot=home&panel=home-all) to [create a tab](/microsoftteams/platform/concepts/tabs/tabs-overview) that uses the existing website code.

Microsoft Teams APIs can enhance apps inside and outside of Teams:

|App type|Scenario description|
|:-------|:-------------------|
| [Tabs](/microsoftteams/platform/concepts/tabs/tabs-overview) |Surface your content in Microsoft Teams.|
| [Bots](/microsoftteams/platform/concepts/bots/bots-overview) |Help users get tasks done in conversations.|
| [Connectors](/microsoftteams/platform/concepts/connectors/connectors) |Post updates from external services to channels.|
| [Actionable messaging](/microsoftteams/platform/concepts/cards/cards) |Add enhanced interaction to your connector cards.|
| [Messaging extensions](/microsoftteams/platform/concepts/messaging-extensions) |Allow users to query and share information in conversations.|
|Websites| Surface enhanced content in your webpages.|
|Services|Enhance your client applications with Microsoft Graph data via your web service.|
| [Activity feed](/microsoftteams/platform/concepts/activity-feed)|Engage users via feed notifications.|
| [Calling and online meetings (preview)](/graph/api/resources/communications-api-overview) |Create Microsoft Teams apps with bots that can initiate and participate in audio/video calls, route/transfer calls based on interactive voice response (IVR) flows, and participate in online meetings.|

## Get notified about changes

Microsoft Teams supports subscribing to changes (create, update, and delete) to messages in [channels](/graph/api/resources/channel) and [chats](/graph/api/resources/chat) to allow apps to get near-instant updates. For details about how to subscribe to changes, see [Get change notifications for messages in channels and chats](teams-changenotifications-chatmessage.md).

## Enable employee learning using the collaborative capabilities in Teams
Viva Learning built for Microsoft Teams and Microsoft 365 brings employee learning into the flow of work. Viva Learning lets employers register learning providers, upload and manage content metadata, learner assignments, and completion records. Employees can share learning content in Teams messages, meeting chats, or emails, encouraging peer learning and mentoring conversations. 

Use the employee learning APIs for Viva Learning to: 
- Register and manage a [learning provider](/graph/api/resources/learningprovider).
- Insert, update, retrieve, and delete [learning content](/graph/api/resources/learningcontent) metadata.

## API reference

Looking for the API reference for Teams and Viva Learning?

- [Teams API in Microsoft Graph v1.0](/graph/api/resources/teams-api-overview)
- [Teams API in Microsoft Graph beta](/graph/api/resources/teams-api-overview?view=graph-rest-beta&preserve-view=true)
- [Use the employee learning API to integrate with Viva Learning](/graph/api/resources/viva-learning-api-overview)

## Next steps

- Watch the [overview video](https://aka.ms/teamsgraph/v1/video).
- Learn how to [use the Microsoft Teams API](/graph/api/resources/teams-api-overview).
- Drill down on the methods, properties, and relationships of the [team](/graph/api/resources/team), [channel](/graph/api/resources/channel), and [group](/graph/api/resources/group) resources.
- Try the API in the [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).
- Read more about the [Microsoft Teams programming model](/microsoftteams/platform/concepts/concepts-overview).
- Explore the [cloud communications APIs](/graph/api/resources/communications-api-overview).
- Get a jump-start with sample code: [Contoso Airlines](https://github.com/microsoftgraph/contoso-airlines-teams-sample), [C# mini-samples](https://github.com/microsoftgraph/csharp-teams-sample-graph)
