---
description: "Automatically generated file. DO NOT MODIFY"
---

```java

GraphServiceClient graphClient = GraphServiceClient.builder().authenticationProvider( authProvider ).buildClient();

MailSearchFolder mailFolder = new MailSearchFolder();
mailFolder.filterQuery = "contains(subject, 'Analytics')";

graphClient.me().mailFolders("AAMkAGVmMDEzM")
	.buildRequest()
	.patch(mailFolder);

```