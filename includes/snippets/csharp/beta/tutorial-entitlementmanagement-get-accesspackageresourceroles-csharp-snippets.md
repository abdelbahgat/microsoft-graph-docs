---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

// Code snippets are only available for the latest version. Current version is 5.x

// To initialize your graphClient, see https://learn.microsoft.com/en-us/graph/sdks/create-client?from=snippets&tabs=csharp
var result = await graphClient.IdentityGovernance.EntitlementManagement.AccessPackageCatalogs["{accessPackageCatalog-id}"].AccessPackageResourceRoles.GetAsync((requestConfiguration) =>
{
	requestConfiguration.QueryParameters.Filter = "(originSystem eq 'AadGroup' and accessPackageResource/id eq '4a1e21c5-8a76-4578-acb1-641160e076e8' and displayName eq 'Member')";
	requestConfiguration.QueryParameters.Expand = new string []{ "accessPackageResource" };
});


```