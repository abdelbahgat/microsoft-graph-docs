---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(credentials, scopes)

request_body = TeamworkTag(
	display_name = "Finance",
	members = [
		TeamworkTagMember(
			user_id = "92f6952f-61ca-4a94-8910-508a240bc167",
		),
		TeamworkTagMember(
			user_id = "085d800c-b86b-4bfc-a857-9371ad1caf29",
		),
	],
)

result = await graph_client.teams.by_team_id('team-id').tags.post(request_body)


```