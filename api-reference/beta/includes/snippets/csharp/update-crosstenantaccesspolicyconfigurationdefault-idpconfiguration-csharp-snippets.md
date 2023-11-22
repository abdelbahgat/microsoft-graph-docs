---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

// Code snippets are only available for the latest version. Current version is 5.x

// Dependencies
using Microsoft.Graph.Beta.Models;

var requestBody = new CrossTenantAccessPolicyConfigurationDefault
{
	InvitationRedemptionIdentityProviderConfiguration = new DefaultInvitationRedemptionIdentityProviderConfiguration
	{
		PrimaryIdentityProviderPrecedenceOrder = new List<B2bIdentityProvidersType?>
		{
			B2bIdentityProvidersType.ExternalFederation,
			B2bIdentityProvidersType.AzureActiveDirectory,
			B2bIdentityProvidersType.SocialIdentityProviders,
		},
		FallbackIdentityProvider = B2bIdentityProvidersType.DefaultConfiguredIdp,
	},
};

// To initialize your graphClient, see https://learn.microsoft.com/en-us/graph/sdks/create-client?from=snippets&tabs=csharp
var result = await graphClient.Policies.CrossTenantAccessPolicy.Default.PatchAsync(requestBody);


```