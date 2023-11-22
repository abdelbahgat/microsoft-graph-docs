---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(credentials, scopes)

query_params = AlertIncidentsRequestBuilder.AlertIncidentsRequestBuilderGetQueryParameters(
		top = 5,
)

request_configuration = AlertIncidentsRequestBuilder.AlertIncidentsRequestBuilderGetRequestConfiguration(
query_parameters = query_params,
)

result = await graph_client.identity_governance.role_management_alerts.alerts.by_unified_role_management_alert_id('unifiedRoleManagementAlert-id').alert_incidents.get(request_configuration = request_configuration)


```