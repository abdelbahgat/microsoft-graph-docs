---
description: "Automatically generated file. DO NOT MODIFY"
---

```java

GraphServiceClient graphClient = GraphServiceClient.builder().authenticationProvider( authProvider ).buildClient();

CloudPC cloudPC = graphClient.me().cloudPCs("36bd4942-0ca8-11ed-861d-0242ac120002")
	.buildRequest()
	.get();

```