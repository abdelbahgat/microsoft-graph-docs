---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
import (
	  "context"
	  msgraphsdk "github.com/microsoftgraph/msgraph-sdk-go"
	  graphmodels "github.com/microsoftgraph/msgraph-sdk-go/Communications/Calls/Item/Answer"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)


requestBody := graphmodels.NewAnswerPostRequestBody()
callbackUri := "https://bot.contoso.com/api/calls"
requestBody.SetCallbackUri(&callbackUri) 
acceptedModalities := []graphmodels.Modalityable {
	modality := graphmodels.AUDIO_MODALITY 
	requestBody.SetModality(&modality) 

}
requestBody.SetAcceptedModalities(acceptedModalities)
mediaConfig := graphmodels.NewMediaConfig()
additionalData := map[string]interface{}{


 := graphmodels.New()
uri := "https://cdn.contoso.com/beep.wav"
.SetUri(&uri) 
resourceId := "1D6DE2D4-CD51-4309-8DAA-70768651088E"
.SetResourceId(&resourceId) 
 := graphmodels.New()
uri := "https://cdn.contoso.com/cool.wav"
.SetUri(&uri) 
resourceId := "1D6DE2D4-CD51-4309-8DAA-70768651088F"
.SetResourceId(&resourceId) 

	preFetchMedia := []graphmodels.Objectable {
		,
		,

	}
}
mediaConfig.SetAdditionalData(additionalData)
requestBody.SetMediaConfig(mediaConfig)

graphClient.Communications().Calls().ByCallId("call-id").Answer().Post(context.Background(), requestBody, nil)


```