---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

// Code snippets are only available for the latest version. Current version is 5.x

// Dependencies
using Microsoft.Graph.Beta.Models.IdentityGovernance;
using Microsoft.Graph.Beta.Models;

var requestBody = new Workflow
{
	Category = LifecycleWorkflowCategory.Leaver,
	DisplayName = "Post-Offboarding of an employee",
	Description = "Configure offboarding tasks for employees after their last day of work",
	IsEnabled = true,
	IsSchedulingEnabled = false,
	ExecutionConditions = new TriggerAndScopeBasedConditions
	{
		OdataType = "#microsoft.graph.identityGovernance.triggerAndScopeBasedConditions",
		Scope = new RuleBasedSubjectSet
		{
			OdataType = "#microsoft.graph.identityGovernance.ruleBasedSubjectSet",
			Rule = "department eq 'Marketing'",
		},
		Trigger = new TimeBasedAttributeTrigger
		{
			OdataType = "#microsoft.graph.identityGovernance.timeBasedAttributeTrigger",
			TimeBasedAttribute = WorkflowTriggerTimeBasedAttribute.EmployeeLeaveDateTime,
			OffsetInDays = 7,
		},
	},
	Tasks = new List<TaskObject>
	{
		new TaskObject
		{
			Category = LifecycleTaskCategory.Leaver,
			ContinueOnError = false,
			Description = "Remove all licenses assigned to the user",
			DisplayName = "Remove all licenses for user",
			ExecutionSequence = 1,
			IsEnabled = true,
			TaskDefinitionId = "8fa97d28-3e52-4985-b3a9-a1126f9b8b4e",
			Arguments = new List<KeyValuePair>
			{
			},
		},
		new TaskObject
		{
			Category = LifecycleTaskCategory.Leaver,
			ContinueOnError = false,
			Description = "Remove user from all Teams memberships",
			DisplayName = "Remove user from all Teams",
			ExecutionSequence = 2,
			IsEnabled = true,
			TaskDefinitionId = "81f7b200-2816-4b3b-8c5d-dc556f07b024",
			Arguments = new List<KeyValuePair>
			{
			},
		},
		new TaskObject
		{
			Category = LifecycleTaskCategory.Leaver,
			ContinueOnError = false,
			Description = "Delete user account in Azure AD",
			DisplayName = "Delete User Account",
			ExecutionSequence = 3,
			IsEnabled = true,
			TaskDefinitionId = "8d18588d-9ad3-4c0f-99d0-ec215f0e3dff",
			Arguments = new List<KeyValuePair>
			{
			},
		},
	},
};

// To initialize your graphClient, see https://learn.microsoft.com/en-us/graph/sdks/create-client?from=snippets&tabs=csharp
var result = await graphClient.IdentityGovernance.LifecycleWorkflows.Workflows.PostAsync(requestBody);


```