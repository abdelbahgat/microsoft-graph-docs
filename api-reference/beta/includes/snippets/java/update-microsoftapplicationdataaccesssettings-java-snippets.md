---
description: "Automatically generated file. DO NOT MODIFY"
---

```java

GraphServiceClient graphClient = GraphServiceClient.builder().authenticationProvider( authProvider ).buildClient();

MicrosoftApplicationDataAccessSettings microsoftApplicationDataAccessSettings = new MicrosoftApplicationDataAccessSettings();
microsoftApplicationDataAccessSettings.disabledForGroup = "edbfe4fb-ec70-4300-928f-dbb2ae86c981";

graphClient.organization("{organizationId}").settings().microsoftApplicationDataAccess()
	.buildRequest()
	.patch(microsoftApplicationDataAccessSettings);

```