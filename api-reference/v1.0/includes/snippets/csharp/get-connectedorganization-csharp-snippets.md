---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

var connectedOrganization = await graphClient.IdentityGovernance.EntitlementManagement.ConnectedOrganizations["{connectedOrganization-id}"]
	.Request()
	.GetAsync();

```