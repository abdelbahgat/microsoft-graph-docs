---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(credentials, scopes)

request_body = Event(
	original_start_time_zone = "originalStartTimeZone-value",
	original_end_time_zone = "originalEndTimeZone-value",
	response_status = ResponseStatus(
		response = ResponseType.None,
		time = "2016-10-19T10:37:00Z",
	),
	recurrence = None,
	uid = "iCalUId-value",
	reminder_minutes_before_start = 99,
	is_online_meeting = True,
	online_meeting_provider = OnlineMeetingProviderType.TeamsForBusiness,
	is_reminder_on = True,
	hide_attendees = False,
	categories = [
		"Red category",
	],
)

result = await graph_client.me.events.by_event_id('event-id').patch(request_body)


```