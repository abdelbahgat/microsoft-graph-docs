---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(credentials, scopes)

request_body = ConditionalAccessPolicy(
	display_name = "Block access to EXO non-trusted regions.",
	state = ConditionalAccessPolicyState.Enabled,
	conditions = ConditionalAccessConditionSet(
		client_app_types = [
			ConditionalAccessClientApp.All,
		],
		applications = ConditionalAccessApplications(
			include_applications = [
				"00000002-0000-0ff1-ce00-000000000000",
			],
		),
		users = ConditionalAccessUsers(
			include_groups = [
				"ba8e7ded-8b0f-4836-ba06-8ff1ecc5c8ba",
			],
		),
		locations = ConditionalAccessLocations(
			include_locations = [
				"198ad66e-87b3-4157-85a3-8a7b51794ee9",
			],
		),
	),
	grant_controls = ConditionalAccessGrantControls(
		operator = "OR",
		built_in_controls = [
			ConditionalAccessGrantControl.Block,
		],
	),
)

result = await graph_client.identity.conditional_access.policies.post(request_body)


```