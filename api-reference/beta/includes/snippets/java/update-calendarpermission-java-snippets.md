---
description: "Automatically generated file. DO NOT MODIFY"
---

```java

GraphServiceClient graphClient = GraphServiceClient.builder().authenticationProvider( authProvider ).buildClient();

CalendarPermission calendarPermission = new CalendarPermission();
calendarPermission.role = CalendarRoleType.WRITE;

graphClient.users("{id}").calendar().calendarPermissions("RGVmYXVsdA==")
	.buildRequest()
	.patch(calendarPermission);

```