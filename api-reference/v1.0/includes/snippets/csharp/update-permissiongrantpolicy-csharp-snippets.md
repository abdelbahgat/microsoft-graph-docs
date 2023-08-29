---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

var permissionGrantPolicy = new PermissionGrantPolicy
{
	DisplayName = "Custom permission grant policy"
};

await graphClient.Policies.PermissionGrantPolicies["{permissionGrantPolicy-id}"]
	.Request()
	.UpdateAsync(permissionGrantPolicy);

```