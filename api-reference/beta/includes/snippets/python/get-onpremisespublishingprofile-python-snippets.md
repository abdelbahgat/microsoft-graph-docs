---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(credentials, scopes)

query_params = OnPremisesPublishingProfileItemRequestBuilder.OnPremisesPublishingProfileItemRequestBuilderGetQueryParameters(
		expand = ["publishedResources","agents","agentGroups"],
)

request_configuration = OnPremisesPublishingProfileItemRequestBuilder.OnPremisesPublishingProfileItemRequestBuilderGetRequestConfiguration(
query_parameters = query_params,
)

result = await graph_client.on_premises_publishing_profiles.by_on_premises_publishing_profile_id('onPremisesPublishingProfile-id').get(request_configuration = request_configuration)


```