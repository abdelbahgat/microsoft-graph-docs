---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

// Code snippets are only available for the latest version. Current version is 5.x

// Dependencies
using Microsoft.Graph.Beta.Models;

var requestBody = new UnifiedRoleAssignment
{
	PrincipalId = "/ServicePrincipals/0451dbb9-6336-42ea-b58f-5953dc053ece",
	RoleDefinitionId = "f66ab1ee-3cac-4d03-8a64-dadc56e563f8",
	DirectoryScopeId = "/AdministrativeUnits/8b532c7a-4d3e-4e99-8ffa-2dfec92c62eb",
	AppScopeId = null,
};

// To initialize your graphClient, see https://learn.microsoft.com/en-us/graph/sdks/create-client?from=snippets&tabs=csharp
var result = await graphClient.RoleManagement.Exchange.RoleAssignments.PostAsync(requestBody);


```