---
description: "Automatically generated file. DO NOT MODIFY"
---

```go


import (
	  "context"
	  msgraphsdk "github.com/microsoftgraph/msgraph-sdk-go"
	  graphmodels "github.com/microsoftgraph/msgraph-sdk-go/models"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)


requestBody := graphmodels.NewCall()
callbackUri := "https://bot.contoso.com/callback"
requestBody.SetCallbackUri(&callbackUri) 
source := graphmodels.NewParticipantInfo()
identity := graphmodels.NewIdentitySet()
additionalData := map[string]interface{}{
applicationInstance := graphmodels.NewIdentity()
displayName := "Calling Bot"
applicationInstance.SetDisplayName(&displayName) 
id := "3d913abb-aec0-4964-8fa6-3c6850c4f278"
applicationInstance.SetId(&id) 
	identity.SetApplicationInstance(applicationInstance)
}
identity.SetAdditionalData(additionalData)
source.SetIdentity(identity)
countryCode := null
source.SetCountryCode(&countryCode) 
endpointType := null
source.SetEndpointType(&endpointType) 
region := null
source.SetRegion(&region) 
languageId := null
source.SetLanguageId(&languageId) 
requestBody.SetSource(source)


invitationParticipantInfo := graphmodels.NewInvitationParticipantInfo()
identity := graphmodels.NewIdentitySet()
additionalData := map[string]interface{}{
phone := graphmodels.NewIdentity()
id := "+12345678901"
phone.SetId(&id) 
	identity.SetPhone(phone)
}
identity.SetAdditionalData(additionalData)
invitationParticipantInfo.SetIdentity(identity)

targets := []graphmodels.InvitationParticipantInfoable {
	invitationParticipantInfo,
}
requestBody.SetTargets(targets)
requestedModalities := []graphmodels.Modalityable {
	modality := graphmodels.AUDIO_MODALITY 
	requestBody.SetModality(&modality)
}
requestBody.SetRequestedModalities(requestedModalities)
mediaConfig := graphmodels.NewAppHostedMediaConfig()
blob := "<Media Session Configuration>"
mediaConfig.SetBlob(&blob) 
requestBody.SetMediaConfig(mediaConfig)
tenantId := "aa67bd4c-8475-432d-bd41-39f255720e0a"
requestBody.SetTenantId(&tenantId) 

calls, err := graphClient.Communications().Calls().Post(context.Background(), requestBody, nil)


```