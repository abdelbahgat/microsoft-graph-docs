---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(credentials, scopes)

request_body = AccessPackageResourceRequest(
	catalog_id = "beedadfe-01d5-4025-910b-84abb9369997",
	request_type = "AdminRemove",
	access_package_resource = AccessPackageResource(
		id = "354078e5-dbce-4894-8af4-0ab274d41662",
	),
)

result = await graph_client.identity_governance.entitlement_management.access_package_resource_requests.post(request_body)


```