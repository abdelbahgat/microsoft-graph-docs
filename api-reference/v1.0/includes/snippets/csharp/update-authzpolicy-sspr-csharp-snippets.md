---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

var authorizationPolicy = new AuthorizationPolicy
{
	AllowedToUseSSPR = true
};

await graphClient.Policies.AuthorizationPolicy
	.Request()
	.UpdateAsync(authorizationPolicy);

```