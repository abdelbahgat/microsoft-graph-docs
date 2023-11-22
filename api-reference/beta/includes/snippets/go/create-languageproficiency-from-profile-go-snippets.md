---
description: "Automatically generated file. DO NOT MODIFY"
---

```go


import (
	  "context"
	  msgraphsdk "github.com/microsoftgraph/msgraph-beta-sdk-go"
	  graphmodels "github.com/microsoftgraph/msgraph-beta-sdk-go/models"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)


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

languages, err := graphClient.Me().Profile().Languages().Post(context.Background(), requestBody, nil)


```