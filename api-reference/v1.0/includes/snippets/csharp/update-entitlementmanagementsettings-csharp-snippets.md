---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

var graphClient = new GraphServiceClient(requestAdapter);

var requestBody = new EntitlementManagementSettings
{
	ExternalUserLifecycleAction = AccessPackageExternalUserLifecycleAction.None,
};
var result = await graphClient.IdentityGovernance.EntitlementManagement.Settings.PatchAsync(requestBody);


```