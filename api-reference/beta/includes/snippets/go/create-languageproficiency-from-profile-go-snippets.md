---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewLanguageProficiency()
displayName := "Norwegian Bokmål"
requestBody.SetDisplayName(&displayName) 
tag := "nb-NO"
requestBody.SetTag(&tag) 
spoken := graphmodels.NATIVEORBILINGUAL_LANGUAGEPROFICIENCYLEVEL 
requestBody.SetSpoken(&spoken) 
written := graphmodels.NATIVEORBILINGUAL_LANGUAGEPROFICIENCYLEVEL 
requestBody.SetWritten(&written) 
reading := graphmodels.NATIVEORBILINGUAL_LANGUAGEPROFICIENCYLEVEL 
requestBody.SetReading(&reading) 

result, err := graphClient.Me().Profile().Languages().Post(requestBody)


```