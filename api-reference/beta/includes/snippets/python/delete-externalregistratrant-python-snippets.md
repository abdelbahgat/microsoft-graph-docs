---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(credentials, scopes)


await graph_client.me.online_meetings.by_online_meeting_id('onlineMeeting-id').registration.registrants.by_meeting_registrant_base_id('meetingRegistrantBase-id').delete()


```