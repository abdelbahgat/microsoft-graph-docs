---
description: "Automatically generated file. DO NOT MODIFY"
---

```java

GraphServiceClient graphClient = GraphServiceClient.builder().authenticationProvider( authProvider ).buildClient();

graphClient.me().outlook().taskGroups("AAMkADIyAAAhrbe-AAA=")
	.buildRequest()
	.delete();

```