---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(credentials, scopes)

query_params = AppliesToRequestBuilder.AppliesToRequestBuilderGetQueryParameters(
		select = ["id","appId","displayName","createdDateTime"],
)

request_configuration = AppliesToRequestBuilder.AppliesToRequestBuilderGetRequestConfiguration(
query_parameters = query_params,
)

result = await graph_client.policies.app_management_policies.by_app_management_policy_id('appManagementPolicy-id').applies_to.get(request_configuration = request_configuration)


```