---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(credentials, scopes)

request_body = B2cIdentityUserFlow(
	is_language_customization_enabled = True,
	default_language_tag = "en",
)

result = await graph_client.identity.b2c_user_flows.by_b2c_identity_user_flow_id('b2cIdentityUserFlow-id').patch(request_body)


```