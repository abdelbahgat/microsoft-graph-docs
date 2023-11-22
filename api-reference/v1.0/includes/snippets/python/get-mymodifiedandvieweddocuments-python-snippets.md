---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(credentials, scopes)

query_params = UsedRequestBuilder.UsedRequestBuilderGetQueryParameters(
		orderby = ["LastUsed/LastAccessedDateTime desc"],
)

request_configuration = UsedRequestBuilder.UsedRequestBuilderGetRequestConfiguration(
query_parameters = query_params,
)

result = await graph_client.me.insights.used.get(request_configuration = request_configuration)


```