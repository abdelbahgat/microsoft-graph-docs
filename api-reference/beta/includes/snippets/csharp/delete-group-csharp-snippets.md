---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

await graphClient.Policies.MobileDeviceManagementPolicies["{mobilityManagementPolicy-id}"].IncludedGroups["{group-id}"].Reference
	.Request()
	.DeleteAsync();

```