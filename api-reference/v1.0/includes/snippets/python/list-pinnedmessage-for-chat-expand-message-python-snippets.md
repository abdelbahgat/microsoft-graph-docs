---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(credentials, scopes)

query_params = PinnedMessagesRequestBuilder.PinnedMessagesRequestBuilderGetQueryParameters(
		expand = ["message"],
)

request_configuration = PinnedMessagesRequestBuilder.PinnedMessagesRequestBuilderGetRequestConfiguration(
query_parameters = query_params,
)

result = await graph_client.chats.by_chat_id('chat-id').pinned_messages.get(request_configuration = request_configuration)


```