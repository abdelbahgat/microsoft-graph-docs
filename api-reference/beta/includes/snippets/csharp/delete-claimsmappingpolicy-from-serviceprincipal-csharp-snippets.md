---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

var graphClient = new GraphServiceClient(requestAdapter);

await graphClient.ServicePrincipals["{servicePrincipal-id}"].ClaimsMappingPolicies["{claimsMappingPolicy-id}"].Ref.DeleteAsync();


```