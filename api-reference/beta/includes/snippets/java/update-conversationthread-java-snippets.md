---
description: "Automatically generated file. DO NOT MODIFY"
---

```java

GraphServiceClient graphClient = GraphServiceClient.builder().authenticationProvider( authProvider ).buildClient();

ConversationThread conversationThread = new ConversationThread();
conversationThread.isLocked = true;

graphClient.groups("{id}").threads("{id}")
	.buildRequest()
	.patch(conversationThread);

```