---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

var connectedOrganization = new ConnectedOrganization
{
	DisplayName = "Connected organization new name",
	Description = "Connected organization new description",
	State = ConnectedOrganizationState.Configured
};

await graphClient.IdentityGovernance.EntitlementManagement.ConnectedOrganizations["{connectedOrganization-id}"]
	.Request()
	.UpdateAsync(connectedOrganization);

```