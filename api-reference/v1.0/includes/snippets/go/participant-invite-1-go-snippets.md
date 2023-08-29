---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewInvitePostRequestBody()


invitationParticipantInfo := graphmodels.NewInvitationParticipantInfo()
additionalData := map[string]interface{}{
	"@odata.type" : "#microsoft.graph.invitationParticipantInfo", 
	"replacesCallId" : "a7ebfb2d-871e-419c-87af-27290b22e8db", 
identity := graphmodels.New()
"@odata.type" := "#microsoft.graph.identitySet"
identity.Set"@odata.type"(&"@odata.type") 
user := graphmodels.New()
"@odata.type" := "#microsoft.graph.identity"
user.Set"@odata.type"(&"@odata.type") 
id := "278405a3-f568-4b3e-b684-009193463064"
user.SetId(&id) 
identityProvider := "AAD"
user.SetIdentityProvider(&identityProvider) 
	identity.SetUser(user)
	invitationParticipantInfo.SetIdentity(identity)
}
invitationParticipantInfo.SetAdditionalData(additionalData)

participants := []graphmodels.InvitationParticipantInfoable {
	invitationParticipantInfo,

}
requestBody.SetParticipants(participants)
clientContext := "f2fa86af-3c51-4bc2-8fc0-475452d9764f"
requestBody.SetClientContext(&clientContext) 

result, err := graphClient.Communications().CallsById("call-id").Participants().Invite(call-id).Post(requestBody)


```