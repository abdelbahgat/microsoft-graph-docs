---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

var userAccountInformation = new UserAccountInformation
{
	CountryCode = "NO"
};

await graphClient.Me.Profile.Account["{userAccountInformation-id}"]
	.Request()
	.UpdateAsync(userAccountInformation);

```