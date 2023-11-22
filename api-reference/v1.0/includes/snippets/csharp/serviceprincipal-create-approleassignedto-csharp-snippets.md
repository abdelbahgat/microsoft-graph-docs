---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

// Code snippets are only available for the latest version. Current version is 5.x

// Dependencies
using Microsoft.Graph.Models;

var requestBody = new AppRoleAssignment
{
	PrincipalId = Guid.Parse("33ad69f9-da99-4bed-acd0-3f24235cb296"),
	ResourceId = Guid.Parse("9028d19c-26a9-4809-8e3f-20ff73e2d75e"),
	AppRoleId = Guid.Parse("ef7437e6-4f94-4a0a-a110-a439eb2aa8f7"),
};

// To initialize your graphClient, see https://learn.microsoft.com/en-us/graph/sdks/create-client?from=snippets&tabs=csharp
var result = await graphClient.ServicePrincipals["{servicePrincipal-id}"].AppRoleAssignedTo.PostAsync(requestBody);


```