---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(credentials, scopes)

request_body = EducationAssignmentResource(
	distribute_for_student_work = False,
	resource = EducationPowerPointResource(
		odata_type = "microsoft.graph.educationPowerPointResource",
		display_name = "state diagram.pptx",
		file_url = "https://graph.microsoft.com/beta/drives/b!OPmUsPgnBUiMIXMxWcj3neC1xck6I5NIsnFxfrLdmXoOOmEQNO79QpIMPdOmY3nf/items/01QTY63RN327OXRN6EVFE2Q5FRJZTN5EOJ",
	),
)

result = await graph_client.education.classes.by_education_class_id('educationClass-id').assignments.by_education_assignment_id('educationAssignment-id').resources.post(request_body)


```