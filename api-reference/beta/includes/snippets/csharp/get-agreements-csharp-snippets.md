---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

var agreements = await graphClient.IdentityGovernance.TermsOfUse.Agreements
	.Request()
	.GetAsync();

```