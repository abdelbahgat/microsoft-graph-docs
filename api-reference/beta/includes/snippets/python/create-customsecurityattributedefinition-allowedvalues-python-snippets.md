---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(credentials, scopes)

request_body = CustomSecurityAttributeDefinition(
	attribute_set = "Engineering",
	description = "Active projects for user",
	is_collection = True,
	is_searchable = True,
	name = "Project",
	status = "Available",
	type = "String",
	use_pre_defined_values_only = True,
	allowed_values = [
		AllowedValue(
			id = "Alpine",
			is_active = True,
		),
		AllowedValue(
			id = "Baker",
			is_active = True,
		),
		AllowedValue(
			id = "Cascade",
			is_active = True,
		),
	],
)

result = await graph_client.directory.custom_security_attribute_definitions.post(request_body)


```