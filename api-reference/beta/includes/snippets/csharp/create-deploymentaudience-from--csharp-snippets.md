---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

var graphClient = new GraphServiceClient(requestAdapter);

var requestBody = new Microsoft.Graph.Beta.Models.WindowsUpdates.DeploymentAudience
{
};
var result = await graphClient.Admin.Windows.Updates.DeploymentAudiences.PostAsync(requestBody);


```