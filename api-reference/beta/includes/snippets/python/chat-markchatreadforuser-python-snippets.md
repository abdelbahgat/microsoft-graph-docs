---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(credentials, scopes)

request_body = MarkChatReadForUserPostRequestBody(
	user = TeamworkUserIdentity(
		id = "d864e79f-a516-4d0f-9fee-0eeb4d61fdc2",
		additional_data = {
				"tenant_id" : "2a690434-97d9-4eed-83a6-f5f13600199a",
		}
	),
)

await graph_client.chats.by_chat_id('chat-id').mark_chat_read_for_user.post(request_body)


```