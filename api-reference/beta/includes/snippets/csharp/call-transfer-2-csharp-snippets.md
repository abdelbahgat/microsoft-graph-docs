---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

// Code snippets are only available for the latest version. Current version is 5.x

// Dependencies
using Microsoft.Graph.Beta.Communications.Calls.Item.Transfer;
using Microsoft.Graph.Beta.Models;

var requestBody = new TransferPostRequestBody
{
	TransferTarget = new InvitationParticipantInfo
	{
		OdataType = "#microsoft.graph.invitationParticipantInfo",
		EndpointType = EndpointType.Default,
		Identity = new IdentitySet
		{
			OdataType = "#microsoft.graph.identitySet",
			User = new Identity
			{
				OdataType = "#microsoft.graph.identity",
				Id = "550fae72-d251-43ec-868c-373732c2704f",
				DisplayName = "Heidi Steen",
				AdditionalData = new Dictionary<string, object>
				{
					{
						"tenantId" , "72f988bf-86f1-41af-91ab-2d7cd011db47"
					},
				},
			},
		},
		ReplacesCallId = "e5d39592-99bd-4db8-bca8-30fb894ec51d",
		AdditionalData = new Dictionary<string, object>
		{
			{
				"languageId" , "en-us"
			},
			{
				"region" , "amer"
			},
		},
	},
};

// To initialize your graphClient, see https://learn.microsoft.com/en-us/graph/sdks/create-client?from=snippets&tabs=csharp
await graphClient.Communications.Calls["{call-id}"].Transfer.PostAsync(requestBody);


```