---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

var educationAssignment = new EducationAssignment
{
	DisplayName = "Reading and review test 09.03 #5",
	Instructions = new EducationItemBody
	{
		ContentType = BodyType.Text,
		Content = "Read chapter 5 and write your review"
	},
	DueDateTime = DateTimeOffset.Parse("2021-09-10T00:00:00Z"),
	AddedStudentAction = EducationAddedStudentAction.None
};

await graphClient.Education.Classes["{educationClass-id}"].Assignments["{educationAssignment-id}"]
	.Request()
	.UpdateAsync(educationAssignment);

```