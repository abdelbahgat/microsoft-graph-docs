---
description: "Automatically generated file. DO NOT MODIFY"
---

```java

GraphServiceClient graphClient = GraphServiceClient.builder().authenticationProvider( authProvider ).buildClient();

WorkPosition workPosition = new WorkPosition();
workPosition.isCurrent = true;

graphClient.me().profile().positions("{id}")
	.buildRequest()
	.patch(workPosition);

```