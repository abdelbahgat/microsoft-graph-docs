---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewPlayPromptPostRequestBody()
clientContext := "d45324c1-fcb5-430a-902c-f20af696537c"
requestBody.SetClientContext(&clientContext) 


prompt := graphmodels.NewPrompt()
additionalData := map[string]interface{}{
	"@odata.type" : "#microsoft.graph.mediaPrompt", 
mediaInfo := graphmodels.New()
"@odata.type" := "#microsoft.graph.mediaInfo"
mediaInfo.Set"@odata.type"(&"@odata.type") 
uri := "https://cdn.contoso.com/beep.wav"
mediaInfo.SetUri(&uri) 
resourceId := "1D6DE2D4-CD51-4309-8DAA-70768651088E"
mediaInfo.SetResourceId(&resourceId) 
	prompt.SetMediaInfo(mediaInfo)
}
prompt.SetAdditionalData(additionalData)

prompts := []graphmodels.Promptable {
	prompt,

}
requestBody.SetPrompts(prompts)
loop := false
requestBody.SetLoop(&loop) 

result, err := graphClient.Communications().CallsById("call-id").PlayPrompt(call-id).Post(requestBody)


```