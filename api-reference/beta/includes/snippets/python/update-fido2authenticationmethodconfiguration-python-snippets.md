---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(credentials, scopes)

request_body = Fido2AuthenticationMethodConfiguration(
	odata_type = "#microsoft.graph.fido2AuthenticationMethodConfiguration",
	state = AuthenticationMethodState.Enabled,
	is_attestation_enforced = True,
)

result = await graph_client.policies.authentication_methods_policy.authentication_method_configurations.by_authentication_method_configuration_id('authenticationMethodConfiguration-id').patch(request_body)


```