---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(credentials, scopes)

query_params = CloudPcOnPremisesConnectionItemRequestBuilder.CloudPcOnPremisesConnectionItemRequestBuilderGetQueryParameters(
		select = ["id","displayName","healthCheckStatus","healthCheckStatusDetails","inUse"],
)

request_configuration = CloudPcOnPremisesConnectionItemRequestBuilder.CloudPcOnPremisesConnectionItemRequestBuilderGetRequestConfiguration(
query_parameters = query_params,
)

result = await graph_client.device_management.virtual_endpoint.on_premises_connections.by_cloud_pc_on_premises_connection_id('cloudPcOnPremisesConnection-id').get(request_configuration = request_configuration)


```