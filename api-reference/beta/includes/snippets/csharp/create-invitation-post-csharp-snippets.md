---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

var invitation = new Invitation
{
	InvitedUserEmailAddress = "admin@fabrikam.com",
	InviteRedirectUrl = "https://myapp.contoso.com"
};

await graphClient.Invitations
	.Request()
	.AddAsync(invitation);

```