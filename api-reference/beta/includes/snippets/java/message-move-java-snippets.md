---
description: "Automatically generated file. DO NOT MODIFY"
---

```java

GraphServiceClient graphClient = GraphServiceClient.builder().authenticationProvider( authProvider ).buildClient();

String destinationId = "deleteditems";

graphClient.me().messages("AAMkADhAAATs28OAAA=")
	.move(MessageMoveParameterSet
		.newBuilder()
		.withDestinationId(destinationId)
		.build())
	.buildRequest()
	.post();

```