---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

// Code snippets are only available for the latest version. Current version is 5.x

// Dependencies
using Microsoft.Graph.Beta.Models;

var requestBody = new GovernanceRoleAssignmentRequest
{
	RoleDefinitionId = "8b4d1d51-08e9-4254-b0a6-b16177aae376",
	ResourceId = "e5e7d29d-5465-45ac-885f-4716a5ee74b5",
	SubjectId = "918e54be-12c4-4f4c-a6d3-2ee0e3661c51",
	AssignmentState = "Active",
	Type = "UserAdd",
	Reason = "Activate the owner role",
	Schedule = new GovernanceSchedule
	{
		Type = "Once",
		StartDateTime = DateTimeOffset.Parse("2018-05-12T23:28:43.537Z"),
		Duration = TimeSpan.Parse("PT9H"),
	},
	LinkedEligibleRoleAssignmentId = "e327f4be-42a0-47a2-8579-0a39b025b394",
};

// To initialize your graphClient, see https://learn.microsoft.com/en-us/graph/sdks/create-client?from=snippets&tabs=csharp
var result = await graphClient.PrivilegedAccess["{privilegedAccess-id}"].RoleAssignmentRequests.PostAsync(requestBody);


```