---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(credentials, scopes)

request_body = ManagedAppOperation(
	odata_type = "#microsoft.graph.managedAppOperation",
	display_name = "Display Name value",
	state = "State value",
	version = "Version value",
)

result = await graph_client.device_app_management.managed_app_registrations.by_managed_app_registration_id('managedAppRegistration-id').operations.by_managed_app_operation_id('managedAppOperation-id').patch(request_body)


```