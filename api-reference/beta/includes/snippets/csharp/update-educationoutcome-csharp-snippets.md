---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

// Code snippets are only available for the latest version. Current version is 5.x

// Dependencies
using Microsoft.Graph.Beta.Models;

var requestBody = new EducationRubricOutcome
{
	OdataType = "#microsoft.graph.educationRubricOutcome",
	RubricQualityFeedback = new List<RubricQualityFeedbackModel>
	{
		new RubricQualityFeedbackModel
		{
			QualityId = "9a145aa8-f3d9-43a1-8f77-5387ff0693f2",
			Feedback = new EducationItemBody
			{
				Content = "This is feedback specific to the first quality of the rubric.",
				ContentType = BodyType.Text,
			},
		},
		new RubricQualityFeedbackModel
		{
			QualityId = "d2331fb2-2761-402e-8de6-93e0afaa076e",
			Feedback = new EducationItemBody
			{
				Content = "This is feedback specific to the second quality of the rubric.",
				ContentType = BodyType.Text,
			},
		},
	},
	RubricQualitySelectedLevels = new List<RubricQualitySelectedColumnModel>
	{
		new RubricQualitySelectedColumnModel
		{
			QualityId = "9a145aa8-f3d9-43a1-8f77-5387ff0693f2",
			ColumnId = "4fb17a1d-5681-46c2-a295-4e305c3eae23",
		},
		new RubricQualitySelectedColumnModel
		{
			QualityId = "d2331fb2-2761-402e-8de6-93e0afaa076e",
			ColumnId = "aac076bf-51ba-48c5-a2e0-ee235b0b9740",
		},
	},
};

// To initialize your graphClient, see https://learn.microsoft.com/en-us/graph/sdks/create-client?from=snippets&tabs=csharp
var result = await graphClient.Education.Classes["{educationClass-id}"].Assignments["{educationAssignment-id}"].Submissions["{educationSubmission-id}"].Outcomes["{educationOutcome-id}"].PatchAsync(requestBody);


```