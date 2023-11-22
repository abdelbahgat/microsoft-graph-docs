---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

// Code snippets are only available for the latest version. Current version is 5.x

// Dependencies
using Microsoft.Graph.Beta.Models;

var requestBody = new OnTokenIssuanceStartCustomExtension
{
	OdataType = "#microsoft.graph.onTokenIssuanceStartCustomExtension",
	DisplayName = "onTokenIssuanceStartCustomExtension",
	Description = "Fetch additional claims from custom user store",
	EndpointConfiguration = new HttpRequestEndpoint
	{
		OdataType = "#microsoft.graph.httpRequestEndpoint",
		TargetUrl = "https://authenticationeventsAPI.contoso.com",
	},
	AuthenticationConfiguration = new AzureAdTokenAuthentication
	{
		OdataType = "#microsoft.graph.azureAdTokenAuthentication",
		ResourceId = "api://authenticationeventsAPI.contoso.com/a13d0fc1-04ab-4ede-b215-63de0174cbb4",
	},
	ClaimsForTokenConfiguration = new List<OnTokenIssuanceStartReturnClaim>
	{
		new OnTokenIssuanceStartReturnClaim
		{
			ClaimIdInApiResponse = "DateOfBirth",
		},
		new OnTokenIssuanceStartReturnClaim
		{
			ClaimIdInApiResponse = "CustomRoles",
		},
	},
};

// To initialize your graphClient, see https://learn.microsoft.com/en-us/graph/sdks/create-client?from=snippets&tabs=csharp
var result = await graphClient.Identity.CustomAuthenticationExtensions["{customAuthenticationExtension-id}"].PatchAsync(requestBody);


```