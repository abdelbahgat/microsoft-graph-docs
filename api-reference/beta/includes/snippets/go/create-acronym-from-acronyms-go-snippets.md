---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewAcronym()
displayName := "DNN"
requestBody.SetDisplayName(&displayName) 
standsFor := "Deep Neural Network"
requestBody.SetStandsFor(&standsFor) 
description := "A deep neural network is a neural network with a certain level of complexity, a neural network with more than two layers."
requestBody.SetDescription(&description) 
webUrl := "http://microsoft.com/deep-neural-network"
requestBody.SetWebUrl(&webUrl) 
state := graphmodels.DRAFT_ANSWERSTATE 
requestBody.SetState(&state) 

result, err := graphClient.Search().Acronyms().Post(requestBody)


```