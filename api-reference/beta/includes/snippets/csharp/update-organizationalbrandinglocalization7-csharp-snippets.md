---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

var organizationalBrandingLocalization = new OrganizationalBrandingLocalization
{
	SignInPageText = "Welcome to Contoso France.",
	UsernameHintText = " "
};

await graphClient.Organization["{organization-id}"].Branding.Localizations["{organizationalBrandingLocalization-id}"]
	.Request()
	.UpdateAsync(organizationalBrandingLocalization);

```