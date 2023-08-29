---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewContact()
givenName := "Pavel"
requestBody.SetGivenName(&givenName) 
surname := "Bansky"
requestBody.SetSurname(&surname) 


emailAddress := graphmodels.NewEmailAddress()
address := "pavelb@fabrikam.onmicrosoft.com"
emailAddress.SetAddress(&address) 
name := "Pavel Bansky"
emailAddress.SetName(&name) 

emailAddresses := []graphmodels.EmailAddressable {
	emailAddress,

}
requestBody.SetEmailAddresses(emailAddresses)
businessPhones := []String {
	"+1 732 555 0102",

}
requestBody.SetBusinessPhones(businessPhones)

result, err := graphClient.Me().Contacts().Post(requestBody)


```