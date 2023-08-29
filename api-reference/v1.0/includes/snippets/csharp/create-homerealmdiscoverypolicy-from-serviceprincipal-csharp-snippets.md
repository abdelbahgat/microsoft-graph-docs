---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

var homeRealmDiscoveryPolicy = new HomeRealmDiscoveryPolicy
{
	AdditionalData = new Dictionary<string, object>()
	{
		{"@odata.id", "https://graph.microsoft.com/v1.0/policies/homeRealmDiscoveryPolicies/cd3d9b57-0aee-4f25-8ee3-ac74ef5986a9"}
	}
};

await graphClient.ServicePrincipals["{servicePrincipal-id}"].HomeRealmDiscoveryPolicies.References
	.Request()
	.AddAsync(homeRealmDiscoveryPolicy);

```