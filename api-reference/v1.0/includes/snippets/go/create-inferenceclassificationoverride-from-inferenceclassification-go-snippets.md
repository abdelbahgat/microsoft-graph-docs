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


requestBody := graphmodels.NewInferenceClassificationOverride()
classifyAs := graphmodels.FOCUSED_INFERENCECLASSIFICATIONTYPE 
requestBody.SetClassifyAs(&classifyAs) 
senderEmailAddress := graphmodels.NewEmailAddress()
name := "Samantha Booth"
senderEmailAddress.SetName(&name) 
address := "samanthab@adatum.onmicrosoft.com"
senderEmailAddress.SetAddress(&address) 
requestBody.SetSenderEmailAddress(senderEmailAddress)

overrides, err := graphClient.Me().InferenceClassification().Overrides().Post(context.Background(), requestBody, nil)


```