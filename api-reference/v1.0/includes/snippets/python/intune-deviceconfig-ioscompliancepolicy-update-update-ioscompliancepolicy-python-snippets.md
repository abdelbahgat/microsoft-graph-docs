---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(credentials, scopes)

request_body = IosCompliancePolicy(
	odata_type = "#microsoft.graph.iosCompliancePolicy",
	description = "Description value",
	display_name = "Display Name value",
	version = 7,
	passcode_block_simple = True,
	passcode_expiration_days = 6,
	passcode_minimum_length = 5,
	passcode_minutes_of_inactivity_before_lock = 5,
	passcode_previous_passcode_block_count = 2,
	passcode_minimum_character_set_count = 0,
	passcode_required_type = RequiredPasswordType.Alphanumeric,
	passcode_required = True,
	os_minimum_version = "Os Minimum Version value",
	os_maximum_version = "Os Maximum Version value",
	security_block_jailbroken_devices = True,
	device_threat_protection_enabled = True,
	device_threat_protection_required_security_level = DeviceThreatProtectionLevel.Secured,
	managed_email_profile_required = True,
)

result = await graph_client.device_management.device_compliance_policies.by_device_compliance_policy_id('deviceCompliancePolicy-id').patch(request_body)


```