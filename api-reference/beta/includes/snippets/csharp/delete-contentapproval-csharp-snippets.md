---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

var graphClient = new GraphServiceClient(requestAdapter);

await graphClient.Admin.Windows.Updates.UpdatePolicies["{updatePolicy-id}"].ComplianceChanges["{complianceChange-id}"].DeleteAsync();


```