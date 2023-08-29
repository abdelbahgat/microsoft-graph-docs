---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

var swapShiftsChangeRequest = new SwapShiftsChangeRequestObject
{
	SenderShiftId = "5ad10161-6524-4c7c-9beb-4e8677ba2f6d",
	SenderMessage = "I can't make my shift, any chance we can swap?",
	RecipientUserId = "567c8ea5-9e32-422a-a663-8270201699cd",
	RecipientShiftId = "e73408ca-3ea5-4bbf-96a8-2e06c95f7a2c"
};

await graphClient.Teams["{team-id}"].Schedule.SwapShiftsChangeRequests
	.Request()
	.Header("Authorization","Bearer {token}")
	.AddAsync(swapShiftsChangeRequest);

```