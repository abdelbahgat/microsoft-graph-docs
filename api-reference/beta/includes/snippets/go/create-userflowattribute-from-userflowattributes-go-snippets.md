---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewIdentityUserFlowAttribute()
displayName := "Hobby"
requestBody.SetDisplayName(&displayName) 
description := "Your hobby"
requestBody.SetDescription(&description) 
dataType := graphmodels.STRING_IDENTITYUSERFLOWATTRIBUTEDATATYPE 
requestBody.SetDataType(&dataType) 

result, err := graphClient.Identity().UserFlowAttributes().Post(requestBody)


```