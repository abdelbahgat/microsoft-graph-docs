---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewItemPhone()
type := graphmodels.OTHER_PHONETYPE 
requestBody.SetType(&type) 

graphClient.UsersById("user-id").Profile().PhonesById("itemPhone-id").Patch(requestBody)


```