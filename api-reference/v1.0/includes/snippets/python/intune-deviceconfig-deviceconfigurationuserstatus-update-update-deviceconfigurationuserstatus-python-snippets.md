---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(credentials, scopes)

request_body = DeviceConfigurationUserStatus(
	odata_type = "#microsoft.graph.deviceConfigurationUserStatus",
	user_display_name = "User Display Name value",
	devices_count = 12,
	status = ComplianceStatus.NotApplicable,
	last_reported_date_time = "2017-01-01T00:00:17.7769392-08:00",
	user_principal_name = "User Principal Name value",
)

result = await graph_client.device_management.device_configurations.by_device_configuration_id('deviceConfiguration-id').user_statuses.by_device_configuration_user_status_id('deviceConfigurationUserStatus-id').patch(request_body)


```