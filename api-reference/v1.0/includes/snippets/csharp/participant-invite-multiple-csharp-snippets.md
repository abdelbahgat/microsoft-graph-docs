---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

var graphClient = new GraphServiceClient(requestAdapter);

var requestBody = new Microsoft.Graph.Communications.Calls.Item.Participants.Invite.InvitePostRequestBody
{
	Participants = new List<InvitationParticipantInfo>
	{
		new InvitationParticipantInfo
		{
			OdataType = "#microsoft.graph.invitationParticipantInfo",
			ReplacesCallId = "a7ebfb2d-871e-419c-87af-27290b22e8db",
			Identity = new IdentitySet
			{
				OdataType = "#microsoft.graph.identitySet",
				User = new Identity
				{
					OdataType = "#microsoft.graph.identity",
					Id = "7e1b4346-85a6-4bdd-abe3-d11c5d420efe",
					DisplayName = "string",
				},
			},
		},
		new InvitationParticipantInfo
		{
			OdataType = "#microsoft.graph.invitationParticipantInfo",
			ReplacesCallId = "a7ebfb2d-871e-419c-87af-27290b22e8db",
			Identity = new IdentitySet
			{
				OdataType = "#microsoft.graph.identitySet",
				User = new Identity
				{
					OdataType = "#microsoft.graph.identity",
					Id = "1e126418-44a0-4a94-a6f8-0efe1ad71acb",
					DisplayName = "string",
				},
			},
		},
	},
	ClientContext = "f2fa86af-3c51-4bc2-8fc0-475452d9764f",
};
var result = await graphClient.Communications.Calls["{call-id}"].Participants.Invite.PostAsync(requestBody);


```