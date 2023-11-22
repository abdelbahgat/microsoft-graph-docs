---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(credentials, scopes)

request_body = AccessReviewScheduleDefinition(
	display_name = "Review access of users and groups to privileged roles",
	description_for_admins = "Review access of users and groups to privileged roles",
	scope = PrincipalResourceMembershipsScope(
		odata_type = "#microsoft.graph.principalResourceMembershipsScope",
		principal_scopes = [
			AccessReviewQueryScope(
				odata_type = "#microsoft.graph.accessReviewQueryScope",
				query = "/users",
				query_type = "MicrosoftGraph",
			),
			AccessReviewQueryScope(
				odata_type = "#microsoft.graph.accessReviewQueryScope",
				query = "/groups",
				query_type = "MicrosoftGraph",
			),
		],
		resource_scopes = [
			AccessReviewQueryScope(
				odata_type = "#microsoft.graph.accessReviewQueryScope",
				query = "/roleManagement/directory/roleDefinitions/fe930be7-5e62-47db-91af-98c3a49a38b1",
				query_type = "MicrosoftGraph",
			),
		],
	),
	reviewers = [
		AccessReviewReviewerScope(
			query = "/users/f674a1c9-4a40-439c-bfa3-4b61a9f29d85",
			query_type = "MicrosoftGraph",
		),
	],
	settings = AccessReviewScheduleSettings(
		mail_notifications_enabled = True,
		reminder_notifications_enabled = True,
		justification_required_on_approval = True,
		default_decision_enabled = False,
		default_decision = "None",
		instance_duration_in_days = 3,
		recommendations_enabled = False,
		recurrence = PatternedRecurrence(
			pattern = RecurrencePattern(
				type = RecurrencePatternType.AbsoluteMonthly,
				interval = 3,
			),
			range = RecurrenceRange(
				type = RecurrenceRangeType.NoEnd,
				start_date = "2022-03-02",
			),
		),
	),
)

result = await graph_client.identity_governance.access_reviews.definitions.post(request_body)


```