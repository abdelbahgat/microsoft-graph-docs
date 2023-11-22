---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(credentials, scopes)

request_body = Group(
	description = "Group with designated owner and members",
	display_name = "Operations group",
	group_types = [
	],
	mail_enabled = False,
	mail_nickname = "operations2019",
	security_enabled = True,
	additional_data = {
			"owners@odata_bind" : [
				"https://graph.microsoft.com/v1.0/users/26be1845-4119-4801-a799-aea79d09f1a2",
			],
			"members@odata_bind" : [
				"https://graph.microsoft.com/v1.0/users/ff7cb387-6688-423c-8188-3da9532a73cc",
				"https://graph.microsoft.com/v1.0/users/69456242-0067-49d3-ba96-9de6f2728e14",
			],
	}
)

result = await graph_client.groups.post(request_body)


```