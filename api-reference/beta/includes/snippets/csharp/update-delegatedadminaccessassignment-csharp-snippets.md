---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

// Code snippets are only available for the latest version. Current version is 5.x

// Dependencies
using Microsoft.Graph.Beta.Models;

var requestBody = new DelegatedAdminAccessAssignment
{
	AccessDetails = new DelegatedAdminAccessDetails
	{
		UnifiedRoles = new List<UnifiedRole>
		{
			new UnifiedRole
			{
				RoleDefinitionId = "88d8e3e3-8f55-4a1e-953a-9b9898b8876b",
			},
			new UnifiedRole
			{
				RoleDefinitionId = "44367163-eba1-44c3-98af-f5787879f96a",
			},
			new UnifiedRole
			{
				RoleDefinitionId = "729827e3-9c14-49f7-bb1b-9608f156bbb8",
			},
		},
	},
};

// To initialize your graphClient, see https://learn.microsoft.com/en-us/graph/sdks/create-client?from=snippets&tabs=csharp
var result = await graphClient.TenantRelationships.DelegatedAdminRelationships["{delegatedAdminRelationship-id}"].AccessAssignments["{delegatedAdminAccessAssignment-id}"].PatchAsync(requestBody, (requestConfiguration) =>
{
	requestConfiguration.Headers.Add("If-Match", "W/\"JyI0NzAwNjg0NS0wMDAwLTE5MDAtMDAwMC02MGY0Yjg4MzAwMDAiJw==\"");
});


```