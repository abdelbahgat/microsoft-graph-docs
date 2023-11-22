---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

// Code snippets are only available for the latest version. Current version is 5.x

// Dependencies
using Microsoft.Graph.Beta.ServicePrincipals.Item.Synchronization.Jobs.Item.ValidateCredentials;
using Microsoft.Graph.Beta.Models;

var requestBody = new ValidateCredentialsPostRequestBody
{
	Credentials = new List<SynchronizationSecretKeyStringValuePair>
	{
		new SynchronizationSecretKeyStringValuePair
		{
			Key = SynchronizationSecret.UserName,
			Value = "user@domain.com",
		},
		new SynchronizationSecretKeyStringValuePair
		{
			Key = SynchronizationSecret.Password,
			Value = "password-value",
		},
	},
};

// To initialize your graphClient, see https://learn.microsoft.com/en-us/graph/sdks/create-client?from=snippets&tabs=csharp
await graphClient.ServicePrincipals["{servicePrincipal-id}"].Synchronization.Jobs["{synchronizationJob-id}"].ValidateCredentials.PostAsync(requestBody);


```