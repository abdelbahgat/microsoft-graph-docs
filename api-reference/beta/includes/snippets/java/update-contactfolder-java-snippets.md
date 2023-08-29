---
description: "Automatically generated file. DO NOT MODIFY"
---

```java

GraphServiceClient graphClient = GraphServiceClient.builder().authenticationProvider( authProvider ).buildClient();

ContactFolder contactFolder = new ContactFolder();
contactFolder.parentFolderId = "parentFolderId-value";
contactFolder.displayName = "displayName-value";

graphClient.me().contactFolders("{id}")
	.buildRequest()
	.patch(contactFolder);

```