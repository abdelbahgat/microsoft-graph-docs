---
description: "Automatically generated file. DO NOT MODIFY"
---

```go


import (
	  "context"
	  abstractions "github.com/microsoft/kiota-abstractions-go"
	  msgraphsdk "github.com/microsoftgraph/msgraph-beta-sdk-go"
	  graphusers "github.com/microsoftgraph/msgraph-beta-sdk-go/users"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)


requestBody := graphusers.NewSetPresencePostRequestBody()
sessionId := "22553876-f5ab-4529-bffb-cfe50aa89f87"
requestBody.SetSessionId(&sessionId) 
availability := "Available"
requestBody.SetAvailability(&availability) 
activity := "Available"
requestBody.SetActivity(&activity) 
expirationDuration , err := abstractions.ParseISODuration("PT1H")
requestBody.SetExpirationDuration(&expirationDuration) 

graphClient.Users().ByUserId("user-id").Presence().SetPresence().Post(context.Background(), requestBody, nil)


```