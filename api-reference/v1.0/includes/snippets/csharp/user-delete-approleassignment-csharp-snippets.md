---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

await graphClient.Users["{user-id}"].AppRoleAssignments["{appRoleAssignment-id}"]
	.Request()
	.DeleteAsync();

```