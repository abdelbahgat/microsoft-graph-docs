---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

var users = await graphClient.Users
	.Request()
	.Filter("identities/any(c:c/issuerAssignedId eq 'j.smith@yahoo.com' and c/issuer eq 'My B2C tenant')")
	.Select("displayName,id")
	.GetAsync();

```