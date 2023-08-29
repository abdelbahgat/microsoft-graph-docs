---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

var addLicenses = new List<AssignedLicense>()
{
	new AssignedLicense
	{
		DisabledPlans = new List<Guid>()
		{
			Guid.Parse("113feb6c-3fe4-4440-bddc-54d774bf0318"),
			Guid.Parse("14ab5db5-e6c4-4b20-b4bc-13e36fd2227f")
		},
		SkuId = Guid.Parse("b05e124f-c7cc-45a0-a6aa-8cf78c946968")
	},
	new AssignedLicense
	{
		DisabledPlans = new List<Guid>()
		{
			Guid.Parse("a413a9ff-720c-4822-98ef-2f37c2a21f4c")
		},
		SkuId = Guid.Parse("c7df2760-2c81-4ef7-b578-5b5392b571df")
	}
};

var removeLicenses = new List<Guid>()
{
};

await graphClient.Groups["{group-id}"]
	.AssignLicense(addLicenses,removeLicenses)
	.Request()
	.PostAsync();

```