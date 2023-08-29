---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewItemAddress()
displayName := "Home"
requestBody.SetDisplayName(&displayName) 
detail := graphmodels.NewPhysicalAddress()
type := graphmodels.HOME_PHYSICALADDRESSTYPE 
detail.SetType(&type) 
postOfficeBox := null
detail.SetPostOfficeBox(&postOfficeBox) 
street := "221B Baker Street"
detail.SetStreet(&street) 
city := "London"
detail.SetCity(&city) 
state := null
detail.SetState(&state) 
countryOrRegion := "United Kingdom"
detail.SetCountryOrRegion(&countryOrRegion) 
postalCode := "E14 3TD"
detail.SetPostalCode(&postalCode) 
requestBody.SetDetail(detail)

result, err := graphClient.Me().Profile().Addresses().Post(requestBody)


```