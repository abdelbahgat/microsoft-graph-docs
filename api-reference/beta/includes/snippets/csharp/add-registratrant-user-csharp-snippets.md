---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

// Code snippets are only available for the latest version. Current version is 5.x

// Dependencies
using Microsoft.Graph.Beta.Models;

var requestBody = new MeetingRegistrant
{
	OdataType = "#microsoft.graph.meetingRegistrant",
	FirstName = "Frederick",
	LastName = "Cormier",
	Email = "frederick.cormier@contoso.com",
	CustomQuestionAnswers = new List<CustomQuestionAnswer>
	{
		new CustomQuestionAnswer
		{
			QuestionId = "MSM5YjlmM2Q4ZS03ZmVkLTRmN3gwMDIw94MDAyMF9hX3gwMDIwX2RldmU=",
			Value = "No",
		},
		new CustomQuestionAnswer
		{
			QuestionId = "MSM5M2E2OWQ1Ni1jZTc4LTQDAwMjBfZGlkX3gwMDIwX3lvdV94MDAyMF8=",
			Value = "Internet",
		},
	},
};

// To initialize your graphClient, see https://learn.microsoft.com/en-us/graph/sdks/create-client?from=snippets&tabs=csharp
var result = await graphClient.Users["{user-id}"].OnlineMeetings["{onlineMeeting-id}"].Registration.Registrants.PostAsync(requestBody);


```