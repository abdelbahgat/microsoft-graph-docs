---
description: "Automatically generated file. DO NOT MODIFY"
---

```java

GraphServiceClient graphClient = GraphServiceClient.builder().authenticationProvider( authProvider ).buildClient();

TodoTaskList todoTaskList = new TodoTaskList();
todoTaskList.displayName = "Vacation Plan";

graphClient.me().todo().lists("AAMkADIyAAAhrbPWAAA=")
	.buildRequest()
	.patch(todoTaskList);

```