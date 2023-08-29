---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

var oAuth2PermissionGrant = new OAuth2PermissionGrant
{
	Scope = "User.ReadBasic.All Group.ReadWrite.All"
};

await graphClient.Oauth2PermissionGrants["{oAuth2PermissionGrant-id}"]
	.Request()
	.UpdateAsync(oAuth2PermissionGrant);

```