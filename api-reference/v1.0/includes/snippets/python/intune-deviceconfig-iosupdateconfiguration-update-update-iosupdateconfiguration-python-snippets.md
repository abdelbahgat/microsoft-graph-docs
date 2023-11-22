---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(credentials, scopes)

request_body = IosUpdateConfiguration(
	odata_type = "#microsoft.graph.iosUpdateConfiguration",
	description = "Description value",
	display_name = "Display Name value",
	version = 7,
	active_hours_start = "12:00:05.5020000",
	active_hours_end = "11:59:00.8990000",
	scheduled_install_days = [
		DayOfWeek.Monday,
	],
	utc_time_offset_in_minutes = 6,
)

result = await graph_client.device_management.device_configurations.by_device_configuration_id('deviceConfiguration-id').patch(request_body)


```