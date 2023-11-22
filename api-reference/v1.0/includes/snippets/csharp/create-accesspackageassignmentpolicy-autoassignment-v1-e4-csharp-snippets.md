---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

// Code snippets are only available for the latest version. Current version is 5.x

// Dependencies
using Microsoft.Graph.Models;

var requestBody = new AccessPackageAssignmentPolicy
{
	DisplayName = "A Policy With Questions",
	Description = "",
	AllowedTargetScope = AllowedTargetScope.AllMemberUsers,
	Expiration = new ExpirationPattern
	{
		Type = ExpirationPatternType.NoExpiration,
	},
	RequestorSettings = new AccessPackageAssignmentRequestorSettings
	{
		EnableTargetsToSelfAddAccess = true,
		EnableTargetsToSelfUpdateAccess = true,
		EnableTargetsToSelfRemoveAccess = true,
	},
	RequestApprovalSettings = new AccessPackageAssignmentApprovalSettings
	{
		IsApprovalRequiredForAdd = true,
		IsApprovalRequiredForUpdate = true,
		Stages = new List<AccessPackageApprovalStage>
		{
			new AccessPackageApprovalStage
			{
				DurationBeforeAutomaticDenial = TimeSpan.Parse("P7D"),
				IsApproverJustificationRequired = false,
				IsEscalationEnabled = false,
				FallbackPrimaryApprovers = new List<SubjectSet>
				{
				},
				EscalationApprovers = new List<SubjectSet>
				{
				},
				FallbackEscalationApprovers = new List<SubjectSet>
				{
				},
				PrimaryApprovers = new List<SubjectSet>
				{
					new SingleUser
					{
						OdataType = "#microsoft.graph.singleUser",
						UserId = "08a551cb-575a-4343-b914-f6e42798bd20",
					},
				},
			},
		},
	},
	Questions = new List<AccessPackageQuestion>
	{
		new AccessPackageMultipleChoiceQuestion
		{
			OdataType = "#microsoft.graph.accessPackageMultipleChoiceQuestion",
			Sequence = 1,
			IsRequired = true,
			IsAnswerEditable = true,
			Text = "What country are you working from?",
			IsMultipleSelectionAllowed = false,
			Choices = new List<AccessPackageAnswerChoice>
			{
				new AccessPackageAnswerChoice
				{
					OdataType = "microsoft.graph.accessPackageAnswerChoice",
					ActualValue = "KE",
					Text = "Kenya",
				},
				new AccessPackageAnswerChoice
				{
					OdataType = "microsoft.graph.accessPackageAnswerChoice",
					ActualValue = "US",
					Text = "United States",
				},
				new AccessPackageAnswerChoice
				{
					OdataType = "microsoft.graph.accessPackageAnswerChoice",
					ActualValue = "GY",
					Text = "Guyana",
				},
				new AccessPackageAnswerChoice
				{
					OdataType = "microsoft.graph.accessPackageAnswerChoice",
					ActualValue = "BD",
					Text = "Bangladesh",
				},
				new AccessPackageAnswerChoice
				{
					OdataType = "microsoft.graph.accessPackageAnswerChoice",
					ActualValue = "JP",
					Text = "Japan",
				},
			},
		},
		new AccessPackageTextInputQuestion
		{
			OdataType = "#microsoft.graph.accessPackageTextInputQuestion",
			Sequence = 2,
			IsRequired = true,
			IsAnswerEditable = true,
			Text = "What do you do for work?",
			Localizations = new List<AccessPackageLocalizedText>
			{
				new AccessPackageLocalizedText
				{
					LanguageCode = "fr-CA",
					Text = "Que fais-tu comme travail?",
				},
			},
			IsSingleLineQuestion = false,
			RegexPattern = "[a-zA-Z]+[a-zA-Z\s]*",
		},
	},
	AccessPackage = new AccessPackage
	{
		Id = "977c7ff4-ef8f-4910-9d31-49048ddf3120",
	},
};

// To initialize your graphClient, see https://learn.microsoft.com/en-us/graph/sdks/create-client?from=snippets&tabs=csharp
var result = await graphClient.IdentityGovernance.EntitlementManagement.AssignmentPolicies.PostAsync(requestBody);


```