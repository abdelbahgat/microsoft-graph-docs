---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewUpdateAdDomainPasswordPostRequestBody()
adDomainPassword := "AdDomainPassword value"
requestBody.SetAdDomainPassword(&adDomainPassword) 

graphClient.DeviceManagement().VirtualEndpoint().OnPremisesConnectionsById("cloudPcOnPremisesConnection-id").UpdateAdDomainPassword(cloudPcOnPremisesConnection-id).Post(requestBody)


```