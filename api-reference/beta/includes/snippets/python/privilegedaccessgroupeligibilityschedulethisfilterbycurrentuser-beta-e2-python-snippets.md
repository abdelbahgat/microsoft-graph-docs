---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(credentials, scopes)

query_params = FilterByCurrentUserWithOnRequestBuilder.FilterByCurrentUserWithOnRequestBuilderGetQueryParameters(
		filter = "groupId eq 'd5f0ad2e-6b34-401b-b6da-0c8fc2c5a3fc' and accessId eq 'member'",
)

request_configuration = FilterByCurrentUserWithOnRequestBuilder.FilterByCurrentUserWithOnRequestBuilderGetRequestConfiguration(
query_parameters = query_params,
)

result = await graph_client.identity_governance.privileged_access.group.eligibility_schedules.filter_by_current_user_with_on("principal").get(request_configuration = request_configuration)


```