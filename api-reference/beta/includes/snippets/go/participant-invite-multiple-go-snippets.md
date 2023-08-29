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
id := "7e1b4346-85a6-4bdd-abe3-d11c5d420efe"
user.SetId(&id) 
identityProvider := "AAD"
user.SetIdentityProvider(&identityProvider) 
	identity.SetUser(user)
	invitationParticipantInfo.SetIdentity(identity)
}
invitationParticipantInfo.SetAdditionalData(additionalData)
invitationParticipantInfo1 := graphmodels.NewInvitationParticipantInfo()
additionalData := map[string]interface{}{
	"@odata.type" : "#microsoft.graph.invitationParticipantInfo", 
	"replacesCallId" : "a7ebfb2d-871e-419c-87af-27290b22e8db", 
identity := graphmodels.New()
"@odata.type" := "#microsoft.graph.identitySet"
identity.Set"@odata.type"(&"@odata.type") 
user := graphmodels.New()
"@odata.type" := "#microsoft.graph.identity"
user.Set"@odata.type"(&"@odata.type") 
id := "1e126418-44a0-4a94-a6f8-0efe1ad71acb"
user.SetId(&id) 
identityProvider := "AAD"
user.SetIdentityProvider(&identityProvider) 
	identity.SetUser(user)
	invitationParticipantInfo1.SetIdentity(identity)
}
invitationParticipantInfo1.SetAdditionalData(additionalData)

participants := []graphmodels.InvitationParticipantInfoable {
	invitationParticipantInfo,
	invitationParticipantInfo1,

}
requestBody.SetParticipants(participants)
clientContext := "f2fa86af-3c51-4bc2-8fc0-475452d9764f"
requestBody.SetClientContext(&clientContext) 

result, err := graphClient.Communications().CallsById("call-id").Participants().Invite(call-id).Post(requestBody)


```