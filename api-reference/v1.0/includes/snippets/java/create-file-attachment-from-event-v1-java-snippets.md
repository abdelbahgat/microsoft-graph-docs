---
description: "Automatically generated file. DO NOT MODIFY"
---

```java

GraphServiceClient graphClient = GraphServiceClient.builder().authenticationProvider( authProvider ).buildClient();

FileAttachment attachment = new FileAttachment();
attachment.name = "menu.txt";
attachment.contentBytes = Base64.getDecoder().decode("base64bWFjIGFuZCBjaGVlc2UgdG9kYXk=");

graphClient.me().events("AAMkAGI1AAAt9AHjAAA=").attachments()
	.buildRequest()
	.post(attachment);

```