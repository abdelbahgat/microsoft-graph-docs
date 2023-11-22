---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

// Code snippets are only available for the latest version. Current version is 5.x

// Dependencies
using Microsoft.Graph.Beta.Models;

var requestBody = new AppleManagedIdentityProvider
{
	OdataType = "microsoft.graph.appleManagedIdentityProvider",
	DisplayName = "Sign in with Apple",
	DeveloperId = "UBF8T346G9",
	ServiceId = "com.microsoft.rts.b2c.test.client",
	KeyId = "99P6D879C4",
	CertificateData = "******",
};

// To initialize your graphClient, see https://learn.microsoft.com/en-us/graph/sdks/create-client?from=snippets&tabs=csharp
var result = await graphClient.Identity.IdentityProviders.PostAsync(requestBody);


```