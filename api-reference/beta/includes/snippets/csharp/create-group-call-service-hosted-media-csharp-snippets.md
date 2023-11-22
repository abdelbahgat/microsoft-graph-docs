---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

// Code snippets are only available for the latest version. Current version is 5.x

// Dependencies
using Microsoft.Graph.Beta.Models;

var requestBody = new Call
{
	OdataType = "#microsoft.graph.call",
	Direction = CallDirection.Outgoing,
	Subject = "Create a group call with service hosted media",
	CallbackUri = "https://bot.contoso.com/callback",
	Source = new ParticipantInfo
	{
		OdataType = "#microsoft.graph.participantInfo",
		Identity = new IdentitySet
		{
			OdataType = "#microsoft.graph.identitySet",
			Application = new Identity
			{
				OdataType = "#microsoft.graph.identity",
				DisplayName = "TestBot",
				Id = "dd3885da-f9ab-486b-bfae-85de3d445555",
			},
		},
	},
	Targets = new List<InvitationParticipantInfo>
	{
		new InvitationParticipantInfo
		{
			OdataType = "#microsoft.graph.invitationParticipantInfo",
			Identity = new IdentitySet
			{
				OdataType = "#microsoft.graph.identitySet",
				User = new Identity
				{
					OdataType = "#microsoft.graph.identity",
					DisplayName = "user1",
					Id = "98da8a1a-1b87-452c-a713-65d3f10b5555",
				},
			},
		},
		new ParticipantInfo
		{
			OdataType = "#microsoft.graph.participantInfo",
			Identity = new IdentitySet
			{
				OdataType = "#microsoft.graph.identitySet",
				User = new Identity
				{
					OdataType = "#microsoft.graph.identity",
					DisplayName = "user2",
					Id = "bf5aae9a-d11d-47a8-93b1-782504c95555",
				},
			},
		},
	},
	RequestedModalities = new List<Modality?>
	{
		Modality.Audio,
	},
	MediaConfig = new ServiceHostedMediaConfig
	{
		OdataType = "#microsoft.graph.serviceHostedMediaConfig",
		RemoveFromDefaultAudioGroup = false,
	},
	TenantId = "aa67bd4c-8475-432d-bd41-39f255720e0a",
};

// To initialize your graphClient, see https://learn.microsoft.com/en-us/graph/sdks/create-client?from=snippets&tabs=csharp
var result = await graphClient.Communications.Calls.PostAsync(requestBody);


```