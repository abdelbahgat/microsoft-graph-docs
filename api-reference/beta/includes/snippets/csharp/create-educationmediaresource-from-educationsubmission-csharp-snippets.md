---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

var graphClient = new GraphServiceClient(requestAdapter);

var requestBody = new EducationSubmissionResource
{
	Resource = new EducationResource
	{
		DisplayName = "category.jpg",
		OdataType = "#microsoft.graph.educationMediaResource",
		AdditionalData = new Dictionary<string, object>
		{
			{
				"fileUrl" , "https://graph.microsoft.com/beta/drives/b!OPmUsPgnBUiMIXMxWcj3neC1xck6I5NIsnFxfrLdmXodJYOAkI7rTLhw7ME_e42J/items/01QTY63RK2WLKUUBAA4ZBKXNBL6QFC2TKG"
			},
		},
	},
};
var result = await graphClient.Education.Classes["{educationClass-id}"].Assignments["{educationAssignment-id}"].Submissions["{educationSubmission-id}"].Resources.PostAsync(requestBody);


```