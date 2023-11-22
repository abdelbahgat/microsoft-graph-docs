---
description: "Automatically generated file. DO NOT MODIFY"
---

```java

GraphServiceClient graphClient = GraphServiceClient.builder().authenticationProvider( authProvider ).buildClient();

Event event = new Event();
event.originalStartTimeZone = "originalStartTimeZone-value";
event.originalEndTimeZone = "originalEndTimeZone-value";
ResponseStatus responseStatus = new ResponseStatus();
responseStatus.response = ResponseType.NONE;
responseStatus.time = OffsetDateTimeSerializer.deserialize("2016-10-19T10:37:00Z");
event.responseStatus = responseStatus;
event.recurrence = null;
event.uid = "iCalUId-value";
event.reminderMinutesBeforeStart = 99;
event.isOnlineMeeting = true;
event.onlineMeetingProvider = OnlineMeetingProviderType.TEAMS_FOR_BUSINESS;
event.isReminderOn = true;
event.hideAttendees = false;
LinkedList<String> categoriesList = new LinkedList<String>();
categoriesList.add("Red category");
event.categories = categoriesList;

graphClient.me().events("{id}")
	.buildRequest()
	.patch(event);

```