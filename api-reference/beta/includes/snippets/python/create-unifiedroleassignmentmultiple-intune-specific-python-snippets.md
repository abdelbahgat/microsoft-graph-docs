---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(credentials, scopes)

request_body = UnifiedRoleAssignmentMultiple(
	odata_type = "#microsoft.graph.unifiedRoleAssignmentMultiple",
	display_name = "My test role assignment 1",
	role_definition_id = "c2cf284d-6c41-4e6b-afac-4b80928c9034",
	principal_ids = [
		"f8ca5a85-489a-49a0-b555-0a6d81e56f0d",
		"c1518aa9-4da5-4c84-a902-a31404023890",
	],
	app_scope_ids = [
		"allDevices",
	],
)

result = await graph_client.role_management.device_management.role_assignments.post(request_body)


```