---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(credentials, scopes)

request_body = AadUserConversationMember(
	odata_type = "#microsoft.graph.aadUserConversationMember",
	visible_history_start_date_time = "2019-04-18T23:51:43.255Z",
	roles = [
		"owner",
	],
	additional_data = {
			"user@odata_bind" : "https://graph.microsoft.com/v1.0/users/jacob@contoso.com",
	}
)

result = await graph_client.chats.by_chat_id('chat-id').members.post(request_body)


```