---
description: "Automatically generated file. DO NOT MODIFY"
---

```java

GraphServiceClient graphClient = GraphServiceClient.builder().authenticationProvider( authProvider ).buildClient();

FileAttachment attachment = new FileAttachment();
attachment.name = "smile";
attachment.contentBytes = Base64.getDecoder().decode("a0b1c76de9f7=");

graphClient.me().messages("AAMkpsDRVK").attachments()
	.buildRequest()
	.post(attachment);

```