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
	CallbackUri = "https://bot.contoso.com/callback",
	Source = new ParticipantInfo
	{
		OdataType = "#microsoft.graph.participantInfo",
		Identity = new IdentitySet
		{
			OdataType = "#microsoft.graph.identitySet",
			AdditionalData = new Dictionary<string, object>
			{
				{
					"applicationInstance" , new Identity
					{
						OdataType = "#microsoft.graph.identity",
						DisplayName = "Calling Bot",
						Id = "3d913abb-aec0-4964-8fa6-3c6850c4f278",
					}
				},
			},
		},
		CountryCode = null,
		EndpointType = null,
		Region = null,
		LanguageId = null,
	},
	Targets = new List<InvitationParticipantInfo>
	{
		new InvitationParticipantInfo
		{
			OdataType = "#microsoft.graph.invitationParticipantInfo",
			Identity = new IdentitySet
			{
				OdataType = "#microsoft.graph.identitySet",
				AdditionalData = new Dictionary<string, object>
				{
					{
						"phone" , new Identity
						{
							OdataType = "#microsoft.graph.identity",
							Id = "+12345678901",
						}
					},
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
	},
	TenantId = "aa67bd4c-8475-432d-bd41-39f255720e0a",
};

// To initialize your graphClient, see https://learn.microsoft.com/en-us/graph/sdks/create-client?from=snippets&tabs=csharp
var result = await graphClient.Communications.Calls.PostAsync(requestBody);


```