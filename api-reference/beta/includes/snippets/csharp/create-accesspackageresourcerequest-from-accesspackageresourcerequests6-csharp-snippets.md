---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

// Code snippets are only available for the latest version. Current version is 5.x

// Dependencies
using Microsoft.Graph.Beta.Models;

var requestBody = new AccessPackageResourceRequest
{
	CatalogId = "26ac0c0a-08bc-4a7b-a313-839f58044ba5",
	RequestType = "AdminAdd",
	Justification = "",
	AccessPackageResource = new AccessPackageResource
	{
		DisplayName = "Faculty cafeteria ordering",
		Description = "Example application",
		Url = "https://myapps.microsoft.com/example.com/signin/Faculty%20cafeteria%20ordering/f1e3b407-942d-4934-9a3f-cef1975cb988/",
		ResourceType = "Application",
		OriginId = "2f1099a6-d4fc-4cc9-a0ef-ddd3f1bf0b7e",
		OriginSystem = "AadApplication",
		Attributes = new List<AccessPackageResourceAttribute>
		{
			new AccessPackageResourceAttribute
			{
				AttributeName = "extension_2b676109c7c74ae2b41549205f1947ed_personalTitle",
				IsEditable = true,
				IsPersistedOnAssignmentRemoval = true,
				AttributeSource = new AccessPackageResourceAttributeQuestion
				{
					OdataType = "#microsoft.graph.accessPackageResourceAttributeQuestion",
					Question = new AccessPackageTextInputQuestion
					{
						OdataType = "#microsoft.graph.accessPackageTextInputQuestion",
						IsRequired = false,
						Sequence = 0,
						IsSingleLineQuestion = true,
						Text = new AccessPackageLocalizedContent
						{
							DefaultText = "Title",
							LocalizedTexts = new List<AccessPackageLocalizedText>
							{
							},
						},
					},
				},
				AttributeDestination = new AccessPackageUserDirectoryAttributeStore
				{
					OdataType = "#microsoft.graph.accessPackageUserDirectoryAttributeStore",
				},
			},
		},
	},
};

// To initialize your graphClient, see https://learn.microsoft.com/en-us/graph/sdks/create-client?from=snippets&tabs=csharp
var result = await graphClient.IdentityGovernance.EntitlementManagement.AccessPackageResourceRequests.PostAsync(requestBody);


```