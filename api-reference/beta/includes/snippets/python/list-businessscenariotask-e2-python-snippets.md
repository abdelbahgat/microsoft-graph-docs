---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(credentials, scopes)

query_params = TasksRequestBuilder.TasksRequestBuilderGetQueryParameters(
		filter = "businessScenarioProperties/externalContextId eq 'Warehouse-CA-36'",
)

request_configuration = TasksRequestBuilder.TasksRequestBuilderGetRequestConfiguration(
query_parameters = query_params,
)

result = await graph_client.solutions.business_scenarios.by_business_scenario_id('businessScenario-id').planner.tasks.get(request_configuration = request_configuration)


```