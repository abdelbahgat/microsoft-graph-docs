---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(credentials, scopes)

query_params = EligibilityScheduleRequestsRequestBuilder.EligibilityScheduleRequestsRequestBuilderGetQueryParameters(
		filter = "groupId eq '2b5ed229-4072-478d-9504-a047ebd4b07d' and principalId eq '3cce9d87-3986-4f19-8335-7ed075408ca2'",
		select = ["principalId","action","groupId"],
)

request_configuration = EligibilityScheduleRequestsRequestBuilder.EligibilityScheduleRequestsRequestBuilderGetRequestConfiguration(
query_parameters = query_params,
)

result = await graph_client.identity_governance.privileged_access.group.eligibility_schedule_requests.get(request_configuration = request_configuration)


```