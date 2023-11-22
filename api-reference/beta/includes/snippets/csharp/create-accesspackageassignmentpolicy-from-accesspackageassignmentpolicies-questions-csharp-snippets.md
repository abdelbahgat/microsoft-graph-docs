---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

// Code snippets are only available for the latest version. Current version is 5.x

// Dependencies
using Microsoft.Graph.Beta.Models;

var requestBody = new AccessPackageAssignmentPolicy
{
	AccessPackageId = "b2eba9a1-b357-42ee-83a8-336522ed6cbf",
	DisplayName = "Users from connected organizations can request",
	Description = "Allow users from configured connected organizations to request and be approved by their sponsors",
	CanExtend = false,
	DurationInDays = 365,
	ExpirationDateTime = null,
	RequestorSettings = new RequestorSettings
	{
		ScopeType = "AllExistingConnectedOrganizationSubjects",
		AcceptRequests = true,
	},
	RequestApprovalSettings = new ApprovalSettings
	{
		IsApprovalRequired = true,
		IsApprovalRequiredForExtension = false,
		IsRequestorJustificationRequired = true,
		ApprovalMode = "SingleStage",
		ApprovalStages = new List<ApprovalStage>
		{
			new ApprovalStage
			{
				ApprovalStageTimeOutInDays = 14,
				IsApproverJustificationRequired = true,
				IsEscalationEnabled = false,
				EscalationTimeInMinutes = 11520,
				PrimaryApprovers = new List<UserSet>
				{
					new GroupMembers
					{
						OdataType = "#microsoft.graph.groupMembers",
						IsBackup = true,
						Id = "d2dcb9a1-a445-42ee-83a8-476522ed6cbf",
						Description = "group for users from connected organizations which have no external sponsor",
					},
					new ExternalSponsors
					{
						OdataType = "#microsoft.graph.externalSponsors",
						IsBackup = false,
					},
				},
			},
		},
	},
	Questions = new List<AccessPackageQuestion>
	{
		new AccessPackageMultipleChoiceQuestion
		{
			IsRequired = false,
			Text = new AccessPackageLocalizedContent
			{
				DefaultText = "what state are you from?",
				LocalizedTexts = new List<AccessPackageLocalizedText>
				{
					new AccessPackageLocalizedText
					{
						Text = "¿De qué estado eres?",
						LanguageCode = "es",
					},
				},
			},
			OdataType = "#microsoft.graph.accessPackageMultipleChoiceQuestion",
			Choices = new List<AccessPackageAnswerChoice>
			{
				new AccessPackageAnswerChoice
				{
					ActualValue = "AZ",
					DisplayValue = new AccessPackageLocalizedContent
					{
						LocalizedTexts = new List<AccessPackageLocalizedText>
						{
							new AccessPackageLocalizedText
							{
								Text = "Arizona",
								LanguageCode = "es",
							},
						},
					},
				},
				new AccessPackageAnswerChoice
				{
					ActualValue = "CA",
					DisplayValue = new AccessPackageLocalizedContent
					{
						LocalizedTexts = new List<AccessPackageLocalizedText>
						{
							new AccessPackageLocalizedText
							{
								Text = "California",
								LanguageCode = "es",
							},
						},
					},
				},
				new AccessPackageAnswerChoice
				{
					ActualValue = "OH",
					DisplayValue = new AccessPackageLocalizedContent
					{
						LocalizedTexts = new List<AccessPackageLocalizedText>
						{
							new AccessPackageLocalizedText
							{
								Text = "Ohio",
								LanguageCode = "es",
							},
						},
					},
				},
			},
			AllowsMultipleSelection = false,
		},
		new AccessPackageTextInputQuestion
		{
			IsRequired = false,
			Text = new AccessPackageLocalizedContent
			{
				DefaultText = "Who is your manager?",
				LocalizedTexts = new List<AccessPackageLocalizedText>
				{
					new AccessPackageLocalizedText
					{
						Text = "por qué necesita acceso a este paquete",
						LanguageCode = "es",
					},
				},
			},
			OdataType = "#microsoft.graph.accessPackageTextInputQuestion",
			IsSingleLineQuestion = false,
		},
	},
};

// To initialize your graphClient, see https://learn.microsoft.com/en-us/graph/sdks/create-client?from=snippets&tabs=csharp
var result = await graphClient.IdentityGovernance.EntitlementManagement.AccessPackageAssignmentPolicies.PostAsync(requestBody);


```