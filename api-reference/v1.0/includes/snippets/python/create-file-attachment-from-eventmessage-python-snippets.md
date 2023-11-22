---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(credentials, scopes)

request_body = FileAttachment(
	odata_type = "microsoft.graph.fileAttachment",
	name = "name-value",
	content_type = "contentType-value",
	is_inline = False,
	content_location = "contentLocation-value",
	content_bytes = base64.urlsafe_b64decode("base64-contentBytes-value"),
)

result = await graph_client.me.messages.by_message_id('message-id').attachments.post(request_body)


```