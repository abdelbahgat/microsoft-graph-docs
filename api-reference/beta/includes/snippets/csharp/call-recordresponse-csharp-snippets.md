---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

// Code snippets are only available for the latest version. Current version is 5.x

// Dependencies
using Microsoft.Graph.Beta.Communications.Calls.Item.RecordResponse;
using Microsoft.Graph.Beta.Models;

var requestBody = new RecordResponsePostRequestBody
{
	BargeInAllowed = true,
	ClientContext = "d45324c1-fcb5-430a-902c-f20af696537c",
	Prompts = new List<Prompt>
	{
		new MediaPrompt
		{
			OdataType = "#microsoft.graph.mediaPrompt",
			MediaInfo = new MediaInfo
			{
				Uri = "https://cdn.contoso.com/beep.wav",
				ResourceId = "1D6DE2D4-CD51-4309-8DAA-70768651088E",
			},
		},
	},
	MaxRecordDurationInSeconds = 10,
	InitialSilenceTimeoutInSeconds = 5,
	MaxSilenceTimeoutInSeconds = 2,
	PlayBeep = true,
	StopTones = new List<string>
	{
		"#",
		"1",
		"*",
	},
};

// To initialize your graphClient, see https://learn.microsoft.com/en-us/graph/sdks/create-client?from=snippets&tabs=csharp
var result = await graphClient.Communications.Calls["{call-id}"].RecordResponse.PostAsync(requestBody);


```