---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(credentials, scopes)

request_body = AadUserConversationMember(
	odata_type = "#microsoft.graph.aadUserConversationMember",
	roles = [
	],
	tenant_id = "a18103d1-a6ef-4f66-ac64-e4ef42ea8681",
	additional_data = {
			"user@odata_bind" : "https://graph.microsoft.com/beta/users/bc3598dd-cce4-4742-ae15-173429951408",
	}
)

result = await graph_client.teams.by_team_id('team-id').channels.by_channel_id('channel-id').members.post(request_body)


```