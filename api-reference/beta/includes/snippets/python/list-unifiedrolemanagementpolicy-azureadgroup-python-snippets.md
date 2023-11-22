---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(credentials, scopes)

query_params = RoleManagementPoliciesRequestBuilder.RoleManagementPoliciesRequestBuilderGetQueryParameters(
		filter = "scopeId eq '60bba733-f09d-49b7-8445-32369aa066b3' and scopeType eq 'Group'",
		expand = ["rules($select=id)"],
)

request_configuration = RoleManagementPoliciesRequestBuilder.RoleManagementPoliciesRequestBuilderGetRequestConfiguration(
query_parameters = query_params,
)

result = await graph_client.policies.role_management_policies.get(request_configuration = request_configuration)


```