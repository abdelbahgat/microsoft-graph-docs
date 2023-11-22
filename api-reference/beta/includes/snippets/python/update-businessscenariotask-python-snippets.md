---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(credentials, scopes)

request_body = BusinessScenarioTask(
	odata_type = "#microsoft.graph.businessScenarioTask",
	title = "Customer order #12010",
	percent_complete = 20,
	priority = 1,
	business_scenario_properties = BusinessScenarioProperties(
		external_object_version = "000003",
	),
)

result = await graph_client.solutions.business_scenarios.by_business_scenario_id('businessScenario-id').planner.tasks.by_business_scenario_task_id('businessScenarioTask-id').patch(request_body)


```