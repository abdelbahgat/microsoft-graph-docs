---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(credentials, scopes)

request_body = ChangePasswordPostRequestBody(
	current_password = "xWwvJ]6NMw+bWH-d",
	new_password = "0eM85N54wFxWwvJ]",
)

await graph_client.me.change_password.post(request_body)


```