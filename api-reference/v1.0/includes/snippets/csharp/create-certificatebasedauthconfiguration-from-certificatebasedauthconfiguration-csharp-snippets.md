---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

var certificateBasedAuthConfiguration = new CertificateBasedAuthConfiguration
{
	CertificateAuthorities = new List<CertificateAuthority>()
	{
		new CertificateAuthority
		{
			IsRootAuthority = true,
			Certificate = Convert.FromBase64String("Binary")
		}
	}
};

await graphClient.Organization["{organization-id}"].CertificateBasedAuthConfiguration
	.Request()
	.AddAsync(certificateBasedAuthConfiguration);

```