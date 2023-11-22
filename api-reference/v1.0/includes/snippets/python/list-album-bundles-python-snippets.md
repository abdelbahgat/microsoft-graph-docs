---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(credentials, scopes)

query_params = BundlesRequestBuilder.BundlesRequestBuilderGetQueryParameters(
		filter = "bundle/album ne null",
)

request_configuration = BundlesRequestBuilder.BundlesRequestBuilderGetRequestConfiguration(
query_parameters = query_params,
)

result = await graph_client.drives.by_drive_id('drive-id').bundles.get(request_configuration = request_configuration)


```