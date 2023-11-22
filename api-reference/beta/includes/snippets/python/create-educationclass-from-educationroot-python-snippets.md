---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(credentials, scopes)

request_body = EducationClass(
	description = "Health Level 1",
	class_code = "Health 501",
	display_name = "Health 1",
	external_id = "11019",
	external_name = "Health Level 1",
	external_source = EducationExternalSource.Sis,
	mail_nickname = "fineartschool.net",
)

result = await graph_client.education.classes.post(request_body)


```