---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

var graphClient = new GraphServiceClient(requestAdapter);

var result = await graphClient.Policies.AuthenticationStrengthPolicies["{authenticationStrengthPolicy-id}"].Usage.GetAsync();


```