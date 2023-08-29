---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewGetMailTipsPostRequestBody()
emailAddresses := []String {
	"danas@contoso.onmicrosoft.com",
	"fannyd@contoso.onmicrosoft.com",

}
requestBody.SetEmailAddresses(emailAddresses)
mailTipsOptions := graphmodels.AUTOMATICREPLIES, MAILBOXFULLSTATUS_MAILTIPSTYPE 
requestBody.SetMailTipsOptions(&mailTipsOptions) 

result, err := graphClient.Me().GetMailTips().Post(requestBody)


```