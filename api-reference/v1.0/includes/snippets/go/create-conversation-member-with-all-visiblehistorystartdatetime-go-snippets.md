---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewConversationMember()
"@odata.type" := "#microsoft.graph.aadUserConversationMember"
requestBody.Set"@odata.type"(&"@odata.type") 
visibleHistoryStartDateTime , err := time.Parse(time.RFC3339, "0001-01-01T00:00:00Z")
requestBody.SetVisibleHistoryStartDateTime(&visibleHistoryStartDateTime) 
roles := []String {
	"owner",

}
requestBody.SetRoles(roles)
additionalData := map[string]interface{}{
	"user@odata.bind" : "https://graph.microsoft.com/v1.0/users/8b081ef6-4792-4def-b2c9-c363a1bf41d5", 
}
requestBody.SetAdditionalData(additionalData)

result, err := graphClient.ChatsById("chat-id").Members().Post(requestBody)


```