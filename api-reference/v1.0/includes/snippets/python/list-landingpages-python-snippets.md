---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(credentials, scopes)

query_params = LandingPagesRequestBuilder.LandingPagesRequestBuilderGetQueryParameters(
		filter = "source eq 'tenant'",
)

request_configuration = LandingPagesRequestBuilder.LandingPagesRequestBuilderGetRequestConfiguration(
query_parameters = query_params,
)

result = await graph_client.security.attack_simulation.landing_pages.get(request_configuration = request_configuration)


```