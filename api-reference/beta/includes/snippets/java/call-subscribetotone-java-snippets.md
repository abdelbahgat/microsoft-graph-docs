---
description: "Automatically generated file. DO NOT MODIFY"
---

```java

GraphServiceClient graphClient = GraphServiceClient.builder().authenticationProvider( authProvider ).buildClient();

String clientContext = "fd1c7836-4d84-4e24-b6aa-23188688cc54";

graphClient.communications().calls("{id}")
	.subscribeToTone(CallSubscribeToToneParameterSet
		.newBuilder()
		.withClientContext(clientContext)
		.build())
	.buildRequest()
	.post();

```