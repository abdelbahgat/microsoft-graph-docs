---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewCall()
"@odata.type" := "#microsoft.graph.call"
requestBody.Set"@odata.type"(&"@odata.type") 
callbackUri := "https://bot.contoso.com/callback"
requestBody.SetCallbackUri(&callbackUri) 
source := graphmodels.NewParticipantInfo()
"@odata.type" := "#microsoft.graph.participantInfo"
source.Set"@odata.type"(&"@odata.type") 
identity := graphmodels.NewIdentitySet()
"@odata.type" := "#microsoft.graph.identitySet"
identity.Set"@odata.type"(&"@odata.type") 
application := graphmodels.NewIdentity()
"@odata.type" := "#microsoft.graph.identity"
application.Set"@odata.type"(&"@odata.type") 
displayName := "Calling Bot"
application.SetDisplayName(&displayName) 
id := "2891555a-92ff-42e6-80fa-6e1300c6b5c6"
application.SetId(&id) 
identity.SetApplication(application)
source.SetIdentity(identity)
region := null
source.SetRegion(&region) 
languageId := null
source.SetLanguageId(&languageId) 
requestBody.SetSource(source)


invitationParticipantInfo := graphmodels.NewInvitationParticipantInfo()
"@odata.type" := "#microsoft.graph.invitationParticipantInfo"
invitationParticipantInfo.Set"@odata.type"(&"@odata.type") 
identity := graphmodels.NewIdentitySet()
"@odata.type" := "#microsoft.graph.identitySet"
identity.Set"@odata.type"(&"@odata.type") 
user := graphmodels.NewIdentity()
"@odata.type" := "#microsoft.graph.identity"
user.Set"@odata.type"(&"@odata.type") 
displayName := "John"
user.SetDisplayName(&displayName) 
id := "112f7296-5fa4-42ca-bae8-6a692b15d4b8"
user.SetId(&id) 
identity.SetUser(user)
invitationParticipantInfo.SetIdentity(identity)

targets := []graphmodels.InvitationParticipantInfoable {
	invitationParticipantInfo,

}
requestBody.SetTargets(targets)
requestedModalities := []graphmodels.Modalityable {
	"audio",

}
requestBody.SetRequestedModalities(requestedModalities)
mediaConfig := graphmodels.NewMediaConfig()
"@odata.type" := "#microsoft.graph.appHostedMediaConfig"
mediaConfig.Set"@odata.type"(&"@odata.type") 
additionalData := map[string]interface{}{
	"blob" : "<Media Session Configuration>", 
}
mediaConfig.SetAdditionalData(additionalData)
requestBody.SetMediaConfig(mediaConfig)

result, err := graphClient.Communications().Calls().Post(requestBody)


```