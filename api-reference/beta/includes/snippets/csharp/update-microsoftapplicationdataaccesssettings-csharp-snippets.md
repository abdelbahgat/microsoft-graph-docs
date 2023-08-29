---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

var microsoftApplicationDataAccessSettings = new MicrosoftApplicationDataAccessSettings
{
	DisabledForGroup = "edbfe4fb-ec70-4300-928f-dbb2ae86c981"
};

await graphClient.Organization["{organization-id}"].Settings.MicrosoftApplicationDataAccess
	.Request()
	.UpdateAsync(microsoftApplicationDataAccessSettings);

```