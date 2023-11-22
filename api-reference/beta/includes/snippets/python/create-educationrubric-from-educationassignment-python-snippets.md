---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(credentials, scopes)

request_body = ReferenceUpdate(
	odata_id = "https://graph.microsoft.com/v1.0/education/me/rubrics/{id}",
)

await graph_client.education.classes.by_education_class_id('educationClass-id').assignments.by_education_assignment_id('educationAssignment-id').rubric.ref.put(request_body)


```