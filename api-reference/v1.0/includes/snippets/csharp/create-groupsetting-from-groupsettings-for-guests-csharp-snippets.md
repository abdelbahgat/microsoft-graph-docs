---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

var groupSetting = new GroupSetting
{
	TemplateId = "08d542b9-071f-4e16-94b0-74abb372e3d9",
	Values = new List<SettingValue>()
	{
		new SettingValue
		{
			Name = "AllowToAddGuests",
			Value = "false"
		}
	}
};

await graphClient.Groups["{group-id}"].Settings
	.Request()
	.AddAsync(groupSetting);

```