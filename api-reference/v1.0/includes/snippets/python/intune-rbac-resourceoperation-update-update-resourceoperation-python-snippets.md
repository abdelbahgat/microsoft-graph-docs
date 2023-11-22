---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(credentials, scopes)

request_body = ResourceOperation(
	odata_type = "#microsoft.graph.resourceOperation",
	resource_name = "Resource Name value",
	action_name = "Action Name value",
	description = "Description value",
)

result = await graph_client.device_management.resource_operations.by_resource_operation_id('resourceOperation-id').patch(request_body)


```