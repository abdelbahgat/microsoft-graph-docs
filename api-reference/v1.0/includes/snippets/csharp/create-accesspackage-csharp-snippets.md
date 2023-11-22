---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

// Code snippets are only available for the latest version. Current version is 5.x

// Dependencies
using Microsoft.Graph.Models;

var requestBody = new AccessPackage
{
	DisplayName = "sales reps",
	Description = "outside sales representatives",
	IsHidden = false,
	Catalog = new AccessPackageCatalog
	{
		Id = "66584aae-98bb-48cc-9458-7bee5d2a6577",
	},
};

// To initialize your graphClient, see https://learn.microsoft.com/en-us/graph/sdks/create-client?from=snippets&tabs=csharp
var result = await graphClient.IdentityGovernance.EntitlementManagement.AccessPackages.PostAsync(requestBody);


```