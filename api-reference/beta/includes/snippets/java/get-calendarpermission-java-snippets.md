---
description: "Automatically generated file. DO NOT MODIFY"
---

```java

GraphServiceClient graphClient = GraphServiceClient.builder().authenticationProvider( authProvider ).buildClient();

CalendarPermission calendarPermission = graphClient.users("{id}").calendar().calendarPermissions("{id}")
	.buildRequest()
	.get();

```