---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(credentials, scopes)

query_params = CloudPcProvisioningPolicyItemRequestBuilder.CloudPcProvisioningPolicyItemRequestBuilderGetQueryParameters(
		expand = ["assignments"],
)

request_configuration = CloudPcProvisioningPolicyItemRequestBuilder.CloudPcProvisioningPolicyItemRequestBuilderGetRequestConfiguration(
query_parameters = query_params,
)

result = await graph_client.device_management.virtual_endpoint.provisioning_policies.by_cloud_pc_provisioning_policy_id('cloudPcProvisioningPolicy-id').get(request_configuration = request_configuration)


```