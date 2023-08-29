---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

var channel = new Channel
{
	DisplayName = "Architecture Discussion",
	Description = "This channel is where we debate all future architecture plans",
	MembershipType = ChannelMembershipType.Standard
};

await graphClient.Teams["{team-id}"].Channels
	.Request()
	.AddAsync(channel);

```