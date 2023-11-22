---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(credentials, scopes)

query_params = NoncustodialDataSourcesRequestBuilder.NoncustodialDataSourcesRequestBuilderGetQueryParameters(
		expand = ["dataSource"],
)

request_configuration = NoncustodialDataSourcesRequestBuilder.NoncustodialDataSourcesRequestBuilderGetRequestConfiguration(
query_parameters = query_params,
)

result = await graph_client.security.cases.ediscovery_cases.by_ediscovery_case_id('ediscoveryCase-id').noncustodial_data_sources.get(request_configuration = request_configuration)


```