---
description: "Automatically generated file. DO NOT MODIFY"
---

```java

GraphServiceClient graphClient = GraphServiceClient.builder().authenticationProvider( authProvider ).buildClient();

OutlookTaskFolder outlookTaskFolder = new OutlookTaskFolder();
outlookTaskFolder.name = "Charity work";

graphClient.me().outlook().taskFolders("AAMkADIyAAAhrbPWAAA=")
	.buildRequest()
	.patch(outlookTaskFolder);

```