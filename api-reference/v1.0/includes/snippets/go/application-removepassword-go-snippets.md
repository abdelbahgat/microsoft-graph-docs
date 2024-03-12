---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
import (
	  "context"
	  "github.com/google/uuid"
	  msgraphsdk "github.com/microsoftgraph/msgraph-sdk-go"
	  graphmodels "github.com/microsoftgraph/msgraph-sdk-go/Applications/Item/RemovePassword"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)


requestBody := graphmodels.NewRemovePasswordPostRequestBody()
keyId := uuid.MustParse("f0b0b335-1d71-4883-8f98-567911bfdca6")
requestBody.SetKeyId(&keyId) 

graphClient.Applications().ByApplicationId("application-id").RemovePassword().Post(context.Background(), requestBody, nil)


```