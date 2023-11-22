---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(credentials, scopes)

request_body = UnifiedRoleManagementPolicy(
	rules = [
		UnifiedRoleManagementPolicyApprovalRule(
			odata_type = "#microsoft.graph.unifiedRoleManagementPolicyApprovalRule",
			id = "Approval_EndUser_Assignment",
			target = UnifiedRoleManagementPolicyRuleTarget(
				caller = "EndUser",
				operations = [
					"All",
				],
				level = "Assignment",
				inheritable_settings = [
				],
				enforced_settings = [
				],
			),
			setting = ApprovalSettings(
				is_approval_required = True,
				is_approval_required_for_extension = False,
				is_requestor_justification_required = True,
				approval_mode = "SingleStage",
				approval_stages = [
					ApprovalStage(
						approval_stage_time_out_in_days = 1,
						is_approver_justification_required = True,
						escalation_time_in_minutes = 0,
						is_escalation_enabled = False,
						primary_approvers = [
							SingleUser(
								odata_type = "#microsoft.graph.singleUser",
								is_backup = False,
								id = "c277c8cb-6bb7-42e5-a17f-0add9a718151",
								description = None,
							),
						],
						escalation_approvers = [
						],
					),
				],
			),
		),
		UnifiedRoleManagementPolicyAuthenticationContextRule(
			odata_type = "#microsoft.graph.unifiedRoleManagementPolicyAuthenticationContextRule",
			id = "AuthenticationContext_EndUser_Assignment",
			is_enabled = False,
			claim_value = "",
			target = UnifiedRoleManagementPolicyRuleTarget(
				caller = "EndUser",
				operations = [
					"All",
				],
				level = "Assignment",
				inheritable_settings = [
				],
				enforced_settings = [
				],
			),
		),
		UnifiedRoleManagementPolicyEnablementRule(
			odata_type = "#microsoft.graph.unifiedRoleManagementPolicyEnablementRule",
			id = "Enablement_Admin_Eligibility",
			enabled_rules = [
			],
			target = UnifiedRoleManagementPolicyRuleTarget(
				caller = "Admin",
				operations = [
					"All",
				],
				level = "Eligibility",
				inheritable_settings = [
				],
				enforced_settings = [
				],
			),
		),
		UnifiedRoleManagementPolicyExpirationRule(
			odata_type = "#microsoft.graph.unifiedRoleManagementPolicyExpirationRule",
			id = "Expiration_Admin_Eligibility",
			is_expiration_required = True,
			maximum_duration = "P365D",
			target = UnifiedRoleManagementPolicyRuleTarget(
				caller = "Admin",
				operations = [
					"All",
				],
				level = "Eligibility",
				inheritable_settings = [
				],
				enforced_settings = [
				],
			),
		),
		UnifiedRoleManagementPolicyNotificationRule(
			odata_type = "#microsoft.graph.unifiedRoleManagementPolicyNotificationRule",
			id = "Notification_Admin_Admin_Eligibility",
			notification_type = "Email",
			recipient_type = "Admin",
			notification_level = "All",
			is_default_recipients_enabled = True,
			notification_recipients = [
			],
			target = UnifiedRoleManagementPolicyRuleTarget(
				caller = "Admin",
				operations = [
					"All",
				],
				level = "Eligibility",
				inheritable_settings = [
				],
				enforced_settings = [
				],
			),
		),
	],
)

result = await graph_client.policies.role_management_policies.by_unified_role_management_policy_id('unifiedRoleManagementPolicy-id').patch(request_body)


```