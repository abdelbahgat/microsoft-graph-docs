---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(credentials, scopes)

request_body = SettingStateDeviceSummary(
	odata_type = "#microsoft.graph.settingStateDeviceSummary",
	setting_name = "Setting Name value",
	instance_path = "Instance Path value",
	unknown_device_count = 2,
	not_applicable_device_count = 8,
	compliant_device_count = 4,
	remediated_device_count = 5,
	non_compliant_device_count = 7,
	error_device_count = 0,
	conflict_device_count = 3,
)

result = await graph_client.device_management.device_configurations.by_device_configuration_id('deviceConfiguration-id').device_setting_state_summaries.post(request_body)


```