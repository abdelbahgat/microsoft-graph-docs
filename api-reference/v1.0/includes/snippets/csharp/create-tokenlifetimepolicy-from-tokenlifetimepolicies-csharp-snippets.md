---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

var tokenLifetimePolicy = new TokenLifetimePolicy
{
	Definition = new List<String>()
	{
		"definition-value"
	},
	DisplayName = "displayName-value",
	IsOrganizationDefault = true
};

await graphClient.Policies.TokenLifetimePolicies
	.Request()
	.AddAsync(tokenLifetimePolicy);

```