---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(credentials, scopes)

query_params = DecisionsRequestBuilder.DecisionsRequestBuilderGetQueryParameters(
		top = 100,
		skip = 0,
)

request_configuration = DecisionsRequestBuilder.DecisionsRequestBuilderGetRequestConfiguration(
query_parameters = query_params,
)

result = await graph_client.me.pending_access_review_instances.by_access_review_instance_id('accessReviewInstance-id').decisions.get(request_configuration = request_configuration)


```