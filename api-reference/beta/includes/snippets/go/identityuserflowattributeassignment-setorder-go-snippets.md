---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewSetOrderPostRequestBody()
newAssignmentOrder := graphmodels.NewAssignmentOrder()
order := []String {
	"City",
	"extension_GUID_ShoeSize",

}
newAssignmentOrder.SetOrder(order)
requestBody.SetNewAssignmentOrder(newAssignmentOrder)

graphClient.Identity().B2cUserFlowsById("b2cIdentityUserFlow-id").UserAttributeAssignments().SetOrder(b2cIdentityUserFlow-id).Post(requestBody)


```