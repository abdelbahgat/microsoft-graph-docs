---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

// Code snippets are only available for the latest version. Current version is 5.x

// Dependencies
using Microsoft.Graph.Beta.Models;

var requestBody = new AccessPackageAssignmentRequest
{
	RequestType = "UserAdd",
	AccessPackageAssignment = new AccessPackageAssignment
	{
		TargetId = "007d1c7e-7fa8-4e33-b678-5e437acdcddc",
		AssignmentPolicyId = "db440482-1210-4a60-9b55-3ac7a72f63ba",
		AccessPackageId = "88203d16-0e31-41d4-87b2-dd402f1435e9",
	},
};

// To initialize your graphClient, see https://learn.microsoft.com/en-us/graph/sdks/create-client?from=snippets&tabs=csharp
var result = await graphClient.IdentityGovernance.EntitlementManagement.AccessPackageAssignmentRequests.PostAsync(requestBody);


```