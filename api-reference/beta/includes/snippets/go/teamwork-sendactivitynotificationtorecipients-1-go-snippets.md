---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewSendActivityNotificationToRecipientsPostRequestBody()
topic := graphmodels.NewTeamworkActivityTopic()
source := graphmodels.ENTITYURL_TEAMWORKACTIVITYTOPICSOURCE 
topic.SetSource(&source) 
value := "https://graph.microsoft.com/beta/appCatalogs/teamsApps/{teamsAppId}"
topic.SetValue(&value) 
requestBody.SetTopic(topic)
activityType := "pendingFinanceApprovalRequests"
requestBody.SetActivityType(&activityType) 
previewText := graphmodels.NewItemBody()
content := "Internal spending team has a pending finance approval requests"
previewText.SetContent(&content) 
requestBody.SetPreviewText(previewText)


teamworkNotificationRecipient := graphmodels.NewTeamworkNotificationRecipient()
"@odata.type" := "microsoft.graph.aadUserNotificationRecipient"
teamworkNotificationRecipient.Set"@odata.type"(&"@odata.type") 
additionalData := map[string]interface{}{
	"userId" : "569363e2-4e49-4661-87f2-16f245c5d66a", 
}
teamworkNotificationRecipient.SetAdditionalData(additionalData)
teamworkNotificationRecipient1 := graphmodels.NewTeamworkNotificationRecipient()
"@odata.type" := "microsoft.graph.aadUserNotificationRecipient"
teamworkNotificationRecipient1.Set"@odata.type"(&"@odata.type") 
additionalData := map[string]interface{}{
	"userId" : "ab88234e-0874-477c-9638-d144296ed04f", 
}
teamworkNotificationRecipient1.SetAdditionalData(additionalData)
teamworkNotificationRecipient2 := graphmodels.NewTeamworkNotificationRecipient()
"@odata.type" := "microsoft.graph.aadUserNotificationRecipient"
teamworkNotificationRecipient2.Set"@odata.type"(&"@odata.type") 
additionalData := map[string]interface{}{
	"userId" : "01c64f53-69aa-42c7-9b7f-9f75195d6bfc", 
}
teamworkNotificationRecipient2.SetAdditionalData(additionalData)

recipients := []graphmodels.TeamworkNotificationRecipientable {
	teamworkNotificationRecipient,
	teamworkNotificationRecipient1,
	teamworkNotificationRecipient2,

}
requestBody.SetRecipients(recipients)


keyValuePair := graphmodels.NewKeyValuePair()
name := "pendingRequestCount"
keyValuePair.SetName(&name) 
value := "5"
keyValuePair.SetValue(&value) 

templateParameters := []graphmodels.KeyValuePairable {
	keyValuePair,

}
requestBody.SetTemplateParameters(templateParameters)

graphClient.Teamwork().SendActivityNotificationToRecipients().Post(requestBody)


```