---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(credentials, scopes)

request_body = LearningAssignment(
	odata_type = "#microsoft.graph.learningAssignment",
	assigned_date_time = "2021-05-11T22:57:17+00:00",
	assignment_type = AssignmentType.Required,
	assigner_user_id = "cea1684d-57dc-438d-a9d1-e666ec1a7f3d",
	completed_date_time = None,
	completion_percentage = 20,
	due_date_time = DateTimeTimeZone(
		date_time = "2022-09-22T16:05:00.0000000",
		time_zone = "UTC",
	),
	external_course_activity_id = "12a2228a-e020-11ec-9d64-0242ac120002",
	learning_content_id = "57baf9dc-e020-11ec-9d64-0242ac120002",
	learning_provider_id = "01e8f81b-3060-4dec-acf0-0389665a0a38",
	learner_user_id = "7ba2228a-e020-11ec-9d64-0242ac120002",
	notes = ItemBody(
		content_type = BodyType.Text,
		content = "required assignment added for user",
	),
	status = CourseStatus.NotStarted,
)

result = await graph_client.employee_experience.learning_providers.by_learning_provider_id('learningProvider-id').learning_course_activities.post(request_body)


```