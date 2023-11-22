---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(credentials, scopes)

query_params = RecommendationsRequestBuilder.RecommendationsRequestBuilderGetQueryParameters(
		filter = "recommendationType eq 'turnOffPerUserMFA'",
)

request_configuration = RecommendationsRequestBuilder.RecommendationsRequestBuilderGetRequestConfiguration(
query_parameters = query_params,
)

result = await graph_client.directory.recommendations.get(request_configuration = request_configuration)


```