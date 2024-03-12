---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

var graphClient = new GraphServiceClient(requestAdapter);

var requestBody = new Microsoft.Graph.Beta.Me.PendingAccessReviewInstances.Item.BatchRecordDecisions.BatchRecordDecisionsPostRequestBody
{
	Decision = "Approve",
	Justification = "All principals with access need continued access to the resource (Marketing Group) as all the principals are on the marketing team",
	ResourceId = "a5c51e59-3fcd-4a37-87a1-835c0c21488a",
};
await graphClient.Me.PendingAccessReviewInstances["{accessReviewInstance-id}"].BatchRecordDecisions.PostAsync(requestBody);


```