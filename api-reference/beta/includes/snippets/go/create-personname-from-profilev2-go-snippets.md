---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewPersonName()
displayName := "Innocenty Popov"
requestBody.SetDisplayName(&displayName) 
first := "Innocenty"
requestBody.SetFirst(&first) 
initials := "IP"
requestBody.SetInitials(&initials) 
last := "Popov"
requestBody.SetLast(&last) 
languageTag := "en-US"
requestBody.SetLanguageTag(&languageTag) 
maiden := null
requestBody.SetMaiden(&maiden) 

result, err := graphClient.Me().Profile().Names().Post(requestBody)


```