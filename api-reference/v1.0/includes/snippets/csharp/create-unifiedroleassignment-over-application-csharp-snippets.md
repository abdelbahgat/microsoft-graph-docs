---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

// Code snippets are only available for the latest version. Current version is 5.x

// Dependencies
using Microsoft.Graph.Models;

var requestBody = new UnifiedRoleAssignment
{
	OdataType = "#microsoft.graph.unifiedRoleAssignment",
	PrincipalId = "6b937a9d-c731-465b-a844-2d5b5368c161",
	RoleDefinitionId = "9b895d92-2cd3-44c7-9d02-a6ac2d5ea5c3",
	DirectoryScopeId = "/661e1310-bd76-4795-89a7-8f3c8f855bfc",
};

// To initialize your graphClient, see https://learn.microsoft.com/en-us/graph/sdks/create-client?from=snippets&tabs=csharp
var result = await graphClient.RoleManagement.Directory.RoleAssignments.PostAsync(requestBody);


```