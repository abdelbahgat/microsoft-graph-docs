---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(credentials, scopes)

request_body = ReferenceUpdate(
	odata_id = "https://graph.microsoft.com/v1.0/users/6ea91a8d-e32e-41a1-b7bd-d2d185eed0e0",
)

await graph_client.users.by_user_id('user-id').manager.ref.put(request_body)


```