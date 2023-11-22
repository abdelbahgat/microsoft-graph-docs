---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(credentials, scopes)

request_body = Channel(
	display_name = "My First Shared Channel",
	description = "This is my first shared channel",
	membership_type = ChannelMembershipType.Shared,
	members = [
		AadUserConversationMember(
			odata_type = "#microsoft.graph.aadUserConversationMember",
			roles = [
				"owner",
			],
			additional_data = {
					"user@odata_bind" : "https://graph.microsoft.com/v1.0/users('7640023f-fe43-573f-9ff4-84a9efe4acd6')",
			}
		),
	],
)

result = await graph_client.teams.by_team_id('team-id').channels.post(request_body)


```