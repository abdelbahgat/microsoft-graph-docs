---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewEmailThreatSubmission()
"@odata.type" := "#microsoft.graph.emailUrlThreatSubmission"
requestBody.Set"@odata.type"(&"@odata.type") 
category := graphmodels.SPAM_SUBMISSIONCATEGORY 
requestBody.SetCategory(&category) 
recipientEmailAddress := "tifc@a830edad9050849EQTPWBJZXODQ.onmicrosoft.com"
requestBody.SetRecipientEmailAddress(&recipientEmailAddress) 
additionalData := map[string]interface{}{
	"messageUrl" : "https://graph.microsoft.com/beta/users/c52ce8db-3e4b-4181-93c4-7d6b6bffaf60/messages/AAMkADU3MWUxOTU0LWNlOTEt=", 
}
requestBody.SetAdditionalData(additionalData)

result, err := graphClient.Security().ThreatSubmission().EmailThreats().Post(requestBody)


```