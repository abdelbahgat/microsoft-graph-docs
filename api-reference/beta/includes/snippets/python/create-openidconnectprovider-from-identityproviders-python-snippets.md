---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(credentials, scopes)

request_body = OpenIdConnectProvider(
	odata_type = "microsoft.graph.openIdConnectProvider",
	name = "Login with the Contoso identity provider",
	type = "OpenIDConnect",
	client_id = "56433757-cadd-4135-8431-2c9e3fd68ae8",
	client_secret = "12345",
	claims_mapping = ClaimsMapping(
		user_id = "myUserId",
		given_name = "myGivenName",
		surname = "mySurname",
		email = "myEmail",
		display_name = "myDisplayName",
	),
	domain_hint = "mycustomoidc",
	metadata_url = "https://mycustomoidc.com/.well-known/openid-configuration",
	response_mode = OpenIdConnectResponseMode.Form_post,
	response_type = OpenIdConnectResponseTypes.Code,
	scope = "openid",
)

result = await graph_client.identity_providers.post(request_body)


```