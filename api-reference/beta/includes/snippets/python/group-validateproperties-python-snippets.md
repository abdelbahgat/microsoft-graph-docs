---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(credentials, scopes)

request_body = ValidatePropertiesPostRequestBody(
	display_name = "Myprefix_test_mysuffix",
	mail_nickname = "Myprefix_test_mysuffix",
	on_behalf_of_user_id = UUID("onBehalfOfUserId-value"),
)

await graph_client.groups.by_group_id('group-id').validate_properties.post(request_body)


```