---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(credentials, scopes)

request_body = AccessPackageAssignmentPolicy(
	access_package_id = "88203d16-0e31-41d4-87b2-dd402f1435e9",
	display_name = "Specific users",
	description = "Specific users can request assignment",
	access_review_settings = None,
	duration_in_days = 30,
	requestor_settings = RequestorSettings(
		scope_type = "SpecificDirectorySubjects",
		accept_requests = True,
		allowed_requestors = [
			SingleUser(
				odata_type = "#microsoft.graph.singleUser",
				is_backup = False,
				id = "007d1c7e-7fa8-4e33-b678-5e437acdcddc",
				description = "Requestor1",
			),
		],
	),
	request_approval_settings = ApprovalSettings(
		is_approval_required = False,
		is_approval_required_for_extension = False,
		is_requestor_justification_required = False,
		approval_mode = "NoApproval",
		approval_stages = [
		],
	),
)

result = await graph_client.identity_governance.entitlement_management.access_package_assignment_policies.post(request_body)


```