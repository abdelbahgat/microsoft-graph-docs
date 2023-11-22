---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

// Code snippets are only available for the latest version. Current version is 5.x

// Dependencies
using Microsoft.Graph.Models;

var requestBody = new ConditionalAccessPolicy
{
	DisplayName = "Require MFA to EXO from non-compliant devices.",
	State = ConditionalAccessPolicyState.Enabled,
	Conditions = new ConditionalAccessConditionSet
	{
		Applications = new ConditionalAccessApplications
		{
			IncludeApplications = new List<string>
			{
				"00000002-0000-0ff1-ce00-000000000000",
			},
		},
		Users = new ConditionalAccessUsers
		{
			IncludeGroups = new List<string>
			{
				"ba8e7ded-8b0f-4836-ba06-8ff1ecc5c8ba",
			},
		},
	},
	GrantControls = new ConditionalAccessGrantControls
	{
		Operator = "OR",
		BuiltInControls = new List<ConditionalAccessGrantControl?>
		{
			ConditionalAccessGrantControl.Mfa,
		},
	},
};

// To initialize your graphClient, see https://learn.microsoft.com/en-us/graph/sdks/create-client?from=snippets&tabs=csharp
var result = await graphClient.Identity.ConditionalAccess.Policies.PostAsync(requestBody);


```