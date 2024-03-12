---
description: "Automatically generated file. DO NOT MODIFY"
---

```java

GraphServiceClient graphClient = GraphServiceClient.builder().authenticationProvider( authProvider ).buildClient();

Message message = new Message();
message.receivedDateTime = OffsetDateTimeSerializer.deserialize("2016-10-19T10:37:00Z");
message.sentDateTime = OffsetDateTimeSerializer.deserialize("2016-10-19T10:37:00Z");
message.hasAttachments = true;
message.subject = "subject-value";
ItemBody body = new ItemBody();
body.contentType = BodyType.TEXT;
body.content = "content-value";
message.body = body;
message.bodyPreview = "bodyPreview-value";

graphClient.me().mailFolders("{id}").messages()
	.buildRequest()
	.post(message);

```