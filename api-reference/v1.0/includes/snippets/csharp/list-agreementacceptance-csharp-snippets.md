---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

var graphClient = new GraphServiceClient(requestAdapter);

var result = await graphClient.IdentityGovernance.TermsOfUse.Agreements["{agreement-id}"].Acceptances.GetAsync();


```