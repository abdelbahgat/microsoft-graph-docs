---
description: "Automatically generated file. DO NOT MODIFY"
---

```java

GraphServiceClient graphClient = GraphServiceClient.builder().authenticationProvider( authProvider ).buildClient();

ItemEmail itemEmail = graphClient.users("{userId}").profile().emails("{id}")
	.buildRequest()
	.get();

```