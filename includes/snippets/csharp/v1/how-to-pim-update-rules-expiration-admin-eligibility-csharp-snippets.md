---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

// Code snippets are only available for the latest version. Current version is 5.x

// Dependencies
using Microsoft.Graph.Models;

var requestBody = new UnifiedRoleManagementPolicyExpirationRule
{
	OdataType = "#microsoft.graph.unifiedRoleManagementPolicyExpirationRule",
	Id = "Expiration_Admin_Eligibility",
	IsExpirationRequired = true,
	MaximumDuration = TimeSpan.Parse("P90D"),
	Target = new UnifiedRoleManagementPolicyRuleTarget
	{
		OdataType = "microsoft.graph.unifiedRoleManagementPolicyRuleTarget",
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
};

// To initialize your graphClient, see https://learn.microsoft.com/en-us/graph/sdks/create-client?from=snippets&tabs=csharp
var result = await graphClient.Policies.RoleManagementPolicies["{unifiedRoleManagementPolicy-id}"].Rules["{unifiedRoleManagementPolicyRule-id}"].PatchAsync(requestBody);


```