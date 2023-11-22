---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

// Code snippets are only available for the latest version. Current version is 5.x

// Dependencies
using Microsoft.Graph.Models;

var requestBody = new UnifiedRoleManagementPolicy
{
	Rules = new List<UnifiedRoleManagementPolicyRule>
	{
		new UnifiedRoleManagementPolicyApprovalRule
		{
			OdataType = "#microsoft.graph.unifiedRoleManagementPolicyApprovalRule",
			Id = "Approval_EndUser_Assignment",
			Target = new UnifiedRoleManagementPolicyRuleTarget
			{
				Caller = "EndUser",
				Operations = new List<UnifiedRoleManagementPolicyRuleTargetOperations?>
				{
					UnifiedRoleManagementPolicyRuleTargetOperations.All,
				},
				Level = "Assignment",
				InheritableSettings = new List<string>
				{
				},
				EnforcedSettings = new List<string>
				{
				},
			},
			Setting = new ApprovalSettings
			{
				IsApprovalRequired = true,
				IsApprovalRequiredForExtension = false,
				IsRequestorJustificationRequired = true,
				ApprovalMode = "SingleStage",
				ApprovalStages = new List<UnifiedApprovalStage>
				{
					new UnifiedApprovalStage
					{
						ApprovalStageTimeOutInDays = 1,
						IsApproverJustificationRequired = true,
						EscalationTimeInMinutes = 0,
						IsEscalationEnabled = false,
						PrimaryApprovers = new List<SubjectSet>
						{
							new SingleUser
							{
								OdataType = "#microsoft.graph.singleUser",
								Description = null,
								AdditionalData = new Dictionary<string, object>
								{
									{
										"isBackup" , false
									},
									{
										"id" , "c277c8cb-6bb7-42e5-a17f-0add9a718151"
									},
								},
							},
						},
						EscalationApprovers = new List<SubjectSet>
						{
						},
					},
				},
			},
		},
		new UnifiedRoleManagementPolicyAuthenticationContextRule
		{
			OdataType = "#microsoft.graph.unifiedRoleManagementPolicyAuthenticationContextRule",
			Id = "AuthenticationContext_EndUser_Assignment",
			IsEnabled = false,
			ClaimValue = "",
			Target = new UnifiedRoleManagementPolicyRuleTarget
			{
				Caller = "EndUser",
				Operations = new List<UnifiedRoleManagementPolicyRuleTargetOperations?>
				{
					UnifiedRoleManagementPolicyRuleTargetOperations.All,
				},
				Level = "Assignment",
				InheritableSettings = new List<string>
				{
				},
				EnforcedSettings = new List<string>
				{
				},
			},
		},
		new UnifiedRoleManagementPolicyEnablementRule
		{
			OdataType = "#microsoft.graph.unifiedRoleManagementPolicyEnablementRule",
			Id = "Enablement_Admin_Eligibility",
			EnabledRules = new List<string>
			{
			},
			Target = new UnifiedRoleManagementPolicyRuleTarget
			{
				Caller = "Admin",
				Operations = new List<UnifiedRoleManagementPolicyRuleTargetOperations?>
				{
					UnifiedRoleManagementPolicyRuleTargetOperations.All,
				},
				Level = "Eligibility",
				InheritableSettings = new List<string>
				{
				},
				EnforcedSettings = new List<string>
				{
				},
			},
		},
		new UnifiedRoleManagementPolicyExpirationRule
		{
			OdataType = "#microsoft.graph.unifiedRoleManagementPolicyExpirationRule",
			Id = "Expiration_Admin_Eligibility",
			IsExpirationRequired = true,
			MaximumDuration = TimeSpan.Parse("P365D"),
			Target = new UnifiedRoleManagementPolicyRuleTarget
			{
				Caller = "Admin",
				Operations = new List<UnifiedRoleManagementPolicyRuleTargetOperations?>
				{
					UnifiedRoleManagementPolicyRuleTargetOperations.All,
				},
				Level = "Eligibility",
				InheritableSettings = new List<string>
				{
				},
				EnforcedSettings = new List<string>
				{
				},
			},
		},
		new UnifiedRoleManagementPolicyNotificationRule
		{
			OdataType = "#microsoft.graph.unifiedRoleManagementPolicyNotificationRule",
			Id = "Notification_Admin_Admin_Eligibility",
			NotificationType = "Email",
			RecipientType = "Admin",
			NotificationLevel = "All",
			IsDefaultRecipientsEnabled = true,
			NotificationRecipients = new List<string>
			{
			},
			Target = new UnifiedRoleManagementPolicyRuleTarget
			{
				Caller = "Admin",
				Operations = new List<UnifiedRoleManagementPolicyRuleTargetOperations?>
				{
					UnifiedRoleManagementPolicyRuleTargetOperations.All,
				},
				Level = "Eligibility",
				InheritableSettings = new List<string>
				{
				},
				EnforcedSettings = new List<string>
				{
				},
			},
		},
	},
};

// To initialize your graphClient, see https://learn.microsoft.com/en-us/graph/sdks/create-client?from=snippets&tabs=csharp
var result = await graphClient.Policies.RoleManagementPolicies["{unifiedRoleManagementPolicy-id}"].PatchAsync(requestBody);


```