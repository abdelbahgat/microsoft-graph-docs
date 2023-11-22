---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(credentials, scopes)

request_body = AppManagementPolicy(
	display_name = "Credential management policy",
	description = "Cred policy sample",
	is_enabled = True,
	restrictions = AppManagementConfiguration(
		password_credentials = [
			PasswordCredentialConfiguration(
				restriction_type = AppCredentialRestrictionType.PasswordAddition,
				max_lifetime = None,
				restrict_for_apps_created_after_date_time = "2019-10-19T10:37:00Z",
			),
			PasswordCredentialConfiguration(
				restriction_type = AppCredentialRestrictionType.PasswordLifetime,
				max_lifetime = "P4DT12H30M5S",
				restrict_for_apps_created_after_date_time = "2014-10-19T10:37:00Z",
			),
			PasswordCredentialConfiguration(
				restriction_type = AppCredentialRestrictionType.SymmetricKeyAddition,
				max_lifetime = None,
				restrict_for_apps_created_after_date_time = "2019-10-19T10:37:00Z",
			),
			PasswordCredentialConfiguration(
				restriction_type = AppCredentialRestrictionType.SymmetricKeyLifetime,
				max_lifetime = "P4D",
				restrict_for_apps_created_after_date_time = "2014-10-19T10:37:00Z",
			),
		],
		key_credentials = [
			KeyCredentialConfiguration(
				restriction_type = AppKeyCredentialRestrictionType.AsymmetricKeyLifetime,
				max_lifetime = "P90D",
				restrict_for_apps_created_after_date_time = "2014-10-19T10:37:00Z",
			),
		],
	),
)

result = await graph_client.policies.app_management_policies.post(request_body)


```