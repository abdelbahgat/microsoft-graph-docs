---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewPhoneAuthenticationMethod()
phoneNumber := "+1 2065555555"
requestBody.SetPhoneNumber(&phoneNumber) 
phoneType := graphmodels.MOBILE_AUTHENTICATIONPHONETYPE 
requestBody.SetPhoneType(&phoneType) 

result, err := graphClient.Me().Authentication().PhoneMethods().Post(requestBody)


```