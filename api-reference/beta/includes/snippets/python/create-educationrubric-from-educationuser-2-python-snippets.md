---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(credentials, scopes)

request_body = EducationRubric(
	display_name = "Example Points Rubric",
	description = EducationItemBody(
		content = "This is an example of a rubric with points",
		content_type = BodyType.Text,
	),
	levels = [
		RubricLevel(
			display_name = "Good",
			description = EducationItemBody(
				content = "",
				content_type = BodyType.Text,
			),
			grading = EducationAssignmentPointsGradeType(
				odata_type = "#microsoft.graph.educationAssignmentPointsGradeType",
				max_points = 2,
			),
		),
		RubricLevel(
			display_name = "Poor",
			description = EducationItemBody(
				content = "",
				content_type = BodyType.Text,
			),
			grading = EducationAssignmentPointsGradeType(
				odata_type = "#microsoft.graph.educationAssignmentPointsGradeType",
				max_points = 1,
			),
		),
	],
	qualities = [
		RubricQuality(
			description = EducationItemBody(
				content = "Argument",
				content_type = BodyType.Text,
			),
			criteria = [
				RubricCriterion(
					description = EducationItemBody(
						content = "The essay's argument is persuasive.",
						content_type = BodyType.Text,
					),
				),
				RubricCriterion(
					description = EducationItemBody(
						content = "The essay's argument does not make sense.",
						content_type = BodyType.Text,
					),
				),
			],
			weight = 50.0,
		),
		RubricQuality(
			description = EducationItemBody(
				content = "Spelling and Grammar",
				content_type = BodyType.Text,
			),
			criteria = [
				RubricCriterion(
					description = EducationItemBody(
						content = "The essay uses proper spelling and grammar with few or no errors.",
						content_type = BodyType.Text,
					),
				),
				RubricCriterion(
					description = EducationItemBody(
						content = "The essay has numerous errors in spelling and/or grammar.",
						content_type = BodyType.Text,
					),
				),
			],
			weight = 50.0,
		),
	],
	grading = EducationAssignmentPointsGradeType(
		odata_type = "#microsoft.graph.educationAssignmentPointsGradeType",
	),
)

result = await graph_client.education.me.rubrics.post(request_body)


```