---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(credentials, scopes)

request_body = ConnectedOrganization(
	display_name = "Connected organization new name",
	description = "Connected organization new description",
	state = ConnectedOrganizationState.Configured,
)

result = await graph_client.identity_governance.entitlement_management.connected_organizations.by_connected_organization_id('connectedOrganization-id').patch(request_body)


```