---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(credentials, scopes)

request_body = AdminTodo(
	odata_type = "#microsoft.graph.adminTodo",
	settings = TodoSettings(
		odata_type = "microsoft.graph.todoSettings",
		is_push_notification_enabled = True,
		is_external_join_enabled = False,
		is_external_share_enabled = True,
	),
)

result = await graph_client.admin.todo.patch(request_body)


```