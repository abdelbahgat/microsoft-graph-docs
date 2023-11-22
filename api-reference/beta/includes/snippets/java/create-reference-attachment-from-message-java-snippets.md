---
description: "Automatically generated file. DO NOT MODIFY"
---

```java

GraphServiceClient graphClient = GraphServiceClient.builder().authenticationProvider( authProvider ).buildClient();

ReferenceAttachment attachment = new ReferenceAttachment();
attachment.name = "Personal pictures";
attachment.sourceUrl = "https://contoso.com/personal/mario_contoso_net/Documents/Pics";
attachment.providerType = ReferenceAttachmentProvider.ONE_DRIVE_CONSUMER;
attachment.permission = ReferenceAttachmentPermission.EDIT;
attachment.isFolder = false;

graphClient.me().messages("AAMkAGE1M88AADUv0uFAAA=").attachments()
	.buildRequest()
	.post(attachment);

```