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
	DisplayName = "Real-time employee termination",
	Description = "Execute real-time termination tasks for employees on their last day of work",
	IsEnabled = true,
	IsSchedulingEnabled = false,
	ExecutionConditions = new OnDemandExecutionOnly
	{
		OdataType = "#microsoft.graph.identityGovernance.onDemandExecutionOnly",
	},
	Tasks = new List<TaskObject>
	{
		new TaskObject
		{
			ContinueOnError = false,
			Description = "Remove user from all Azure AD groups memberships",
			DisplayName = "Remove user from all groups",
			ExecutionSequence = 1,
			IsEnabled = true,
			TaskDefinitionId = "b3a31406-2a15-4c9a-b25b-a658fa5f07fc",
			Arguments = new List<KeyValuePair>
			{
			},
		},
		new TaskObject
		{
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