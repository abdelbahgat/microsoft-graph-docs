---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

var accessPackageAssignmentPolicy = await graphClient.IdentityGovernance.EntitlementManagement.AccessPackageAssignmentPolicies["{accessPackageAssignmentPolicy-id}"]
	.Request()
	.GetAsync();

```