---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

// Code snippets are only available for the latest version. Current version is 5.x

// Dependencies
using Microsoft.Graph.Models;

var requestBody = new AccessPackageAssignmentPolicy
{
	DisplayName = "New Policy",
	Description = "policy for assignment",
	AllowedTargetScope = AllowedTargetScope.NotSpecified,
	SpecificAllowedTargets = new List<SubjectSet>
	{
	},
	Expiration = new ExpirationPattern
	{
		EndDateTime = null,
		Duration = null,
		Type = ExpirationPatternType.NoExpiration,
	},
	RequestorSettings = new AccessPackageAssignmentRequestorSettings
	{
		EnableTargetsToSelfAddAccess = false,
		EnableTargetsToSelfUpdateAccess = false,
		EnableTargetsToSelfRemoveAccess = false,
		AllowCustomAssignmentSchedule = true,
		EnableOnBehalfRequestorsToAddAccess = false,
		EnableOnBehalfRequestorsToUpdateAccess = false,
		EnableOnBehalfRequestorsToRemoveAccess = false,
		OnBehalfRequestors = new List<SubjectSet>
		{
		},
	},
	RequestApprovalSettings = new AccessPackageAssignmentApprovalSettings
	{
		IsApprovalRequiredForAdd = false,
		IsApprovalRequiredForUpdate = false,
		Stages = new List<AccessPackageApprovalStage>
		{
		},
	},
	AccessPackage = new AccessPackage
	{
		Id = "a2e1ca1e-4e56-47d2-9daa-e2ba8d12a82b",
	},
};

// To initialize your graphClient, see https://learn.microsoft.com/en-us/graph/sdks/create-client?from=snippets&tabs=csharp
var result = await graphClient.IdentityGovernance.EntitlementManagement.AssignmentPolicies.PostAsync(requestBody);


```