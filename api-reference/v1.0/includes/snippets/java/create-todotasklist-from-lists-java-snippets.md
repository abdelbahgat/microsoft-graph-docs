---
description: "Automatically generated file. DO NOT MODIFY"
---

```java

GraphServiceClient graphClient = GraphServiceClient.builder().authenticationProvider( authProvider ).buildClient();

TodoTaskList todoTaskList = new TodoTaskList();
todoTaskList.displayName = "Travel items";

graphClient.me().todo().lists()
	.buildRequest()
	.post(todoTaskList);

```