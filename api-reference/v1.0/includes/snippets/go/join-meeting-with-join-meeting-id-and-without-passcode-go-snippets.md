---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
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
requestedModalities := []graphmodels.Modalityable {
	modality := graphmodels.AUDIO_MODALITY 
	requestBody.SetModality(&modality) 

}
requestBody.SetRequestedModalities(requestedModalities)
mediaConfig := graphmodels.NewMediaConfig()
additionalData := map[string]interface{}{


 := graphmodels.New()
uri := "https://cdn.contoso.com/beep.wav"
.SetUri(&uri) 
resourceId := "f8971b04-b53e-418c-9222-c82ce681a582"
.SetResourceId(&resourceId) 
 := graphmodels.New()
uri := "https://cdn.contoso.com/cool.wav"
.SetUri(&uri) 
resourceId := "86dc814b-c172-4428-9112-60f8ecae1edb"
.SetResourceId(&resourceId) 

	preFetchMedia := []graphmodels.Objectable {
		,
		,

	}
}
mediaConfig.SetAdditionalData(additionalData)
requestBody.SetMediaConfig(mediaConfig)
meetingInfo := graphmodels.NewMeetingInfo()
additionalData := map[string]interface{}{
	"joinMeetingId" : "1234567", 
	passcode := null
meetingInfo.SetPasscode(&passcode) 
}
meetingInfo.SetAdditionalData(additionalData)
requestBody.SetMeetingInfo(meetingInfo)
tenantId := "86dc81db-c112-4228-9222-63f3esaa1edb"
requestBody.SetTenantId(&tenantId) 

result, err := graphClient.Communications().Calls().Post(context.Background(), requestBody, nil)


```