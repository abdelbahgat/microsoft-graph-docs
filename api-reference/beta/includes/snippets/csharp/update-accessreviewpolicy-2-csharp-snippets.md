---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

var graphClient = new GraphServiceClient(requestAdapter);

var requestBody = new AccessReviewPolicy
{
	IsGroupOwnerManagementEnabled = true,
};
var result = await graphClient.IdentityGovernance.AccessReviews.Policy.PatchAsync(requestBody);


```