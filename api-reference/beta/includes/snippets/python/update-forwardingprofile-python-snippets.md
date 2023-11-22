---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(credentials, scopes)

request_body = ForwardingProfile(
	associations = [
		AssociatedBranch(
			odata_type = "#microsoft.graph.networkaccess.associatedBranch",
			branch_id = "88e5a488-92c3-45d6-ba56-e5cfa63677e8",
		),
	],
)

result = await graph_client.network_access.forwarding_profiles.by_forwarding_profile_id('forwardingProfile-id').patch(request_body)


```