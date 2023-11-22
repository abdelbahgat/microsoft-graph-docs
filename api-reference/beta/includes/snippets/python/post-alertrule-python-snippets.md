---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(credentials, scopes)

request_body = AlertRule(
	id = "215c55cc-b1c9-4d36-a870-be5778101714",
	display_name = "Azure network connection failure impacting Cloud PCs",
	severity = RuleSeverityType.Informational,
	is_system_rule = True,
	description = "Azure network connection checks have failed and is potentially impacting existing Cloud PCs and blocking the provisioning of new Cloud PCs",
	enabled = True,
	alert_rule_template = AlertRuleTemplate.CloudPcOnPremiseNetworkConnectionCheckScenario,
	threshold = RuleThreshold(
		aggregation = AggregationType.Count,
		operator = OperatorType.GreaterOrEqual,
		target = 90,
	),
	notification_channels = [
		NotificationChannel(
			notification_channel_type = NotificationChannelType.Portal,
			notification_receivers = [
			],
		),
		NotificationChannel(
			notification_channel_type = NotificationChannelType.Email,
			notification_receivers = [
				NotificationReceiver(
					locale = "en-us",
					contact_information = "serena.davis@contoso.com",
				),
			],
		),
	],
	additional_data = {
			"conditions" : [
				{
						"relationship_type" : "or",
						"condition_category" : "azureNetworkConnectionCheckFailures",
						"aggregation" : "count",
						"operator" : "greaterOrEqual",
						"threshold_value" : "90",
				},
			],
	}
)

result = await graph_client.device_management.monitoring.alert_rules.post(request_body)


```