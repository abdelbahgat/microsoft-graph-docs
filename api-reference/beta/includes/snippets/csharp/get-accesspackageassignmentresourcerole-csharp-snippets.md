---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

var accessPackageAssignmentResourceRole = await graphClient.IdentityGovernance.EntitlementManagement.AccessPackageAssignmentResourceRoles["{accessPackageAssignmentResourceRole-id}"]
	.Request()
	.GetAsync();

```