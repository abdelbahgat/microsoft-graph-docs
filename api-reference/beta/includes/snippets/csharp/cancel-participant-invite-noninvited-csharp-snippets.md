---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

// Code snippets are only available for the latest version. Current version is 5.x

// Dependencies
using Microsoft.Graph.Beta.Communications.Calls.Item.Participants.Invite;
using Microsoft.Graph.Beta.Models;

var requestBody = new InvitePostRequestBody
{
	Participants = new List<InvitationParticipantInfo>
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
					Id = "278405a3-f568-4b3e-b684-009193463064",
					AdditionalData = new Dictionary<string, object>
					{
						{
							"identityProvider" , "AAD"
						},
					},
				},
			},
			ParticipantId = "a7ebfb2d-871e-419c-87af-27290b22e8db",
		},
	},
	ClientContext = "f2fa86af-3c51-4bc2-8fc0-475452d9764f",
};

// To initialize your graphClient, see https://learn.microsoft.com/en-us/graph/sdks/create-client?from=snippets&tabs=csharp
var result = await graphClient.Communications.Calls["{call-id}"].Participants.Invite.PostAsync(requestBody);


```