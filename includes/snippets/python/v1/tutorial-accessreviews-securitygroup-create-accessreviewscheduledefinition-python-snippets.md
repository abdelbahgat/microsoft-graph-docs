---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(credentials, scopes)

request_body = AccessReviewScheduleDefinition(
	display_name = "One-time self-review for members of Building security",
	description_for_admins = "One-time self-review for members of Building security",
	description_for_reviewers = "One-time self-review for members of Building security",
	scope = AccessReviewScope(
		additional_data = {
				"query" : "/groups/eb75ccd2-59ef-48b7-8f76-cc3f33f899f4/transitiveMembers",
				"query_type" : "MicrosoftGraph",
		}
	),
	instance_enumeration_scope = AccessReviewScope(
		additional_data = {
				"query" : "/groups/eb75ccd2-59ef-48b7-8f76-cc3f33f899f4",
				"query_type" : "MicrosoftGraph",
		}
	),
	settings = AccessReviewScheduleSettings(
		mail_notifications_enabled = True,
		reminder_notifications_enabled = True,
		justification_required_on_approval = True,
		default_decision_enabled = True,
		default_decision = "Deny",
		instance_duration_in_days = 5,
		auto_apply_decisions_enabled = True,
		recommendations_enabled = True,
		recurrence = PatternedRecurrence(
			pattern = None,
			range = RecurrenceRange(
				type = RecurrenceRangeType.Numbered,
				number_of_occurrences = 0,
				recurrence_time_zone = None,
				start_date = "2022-02-11",
				end_date = "2022-02-16",
			),
		),
	),
)

result = await graph_client.identity_governance.access_reviews.definitions.post(request_body)


```