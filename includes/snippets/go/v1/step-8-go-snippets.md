---
description: "Automatically generated file. DO NOT MODIFY"
---

```go


import (
	  "context"
	  "time"
	  msgraphsdk "github.com/microsoftgraph/msgraph-sdk-go"
	  graphmodels "github.com/microsoftgraph/msgraph-sdk-go/models"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)


requestBody := graphmodels.NewSubscription()
expirationDateTime , err := time.Parse(time.RFC3339, "2023-01-12T18:23:45.9356913Z")
requestBody.SetExpirationDateTime(&expirationDateTime) 

subscriptions, err := graphClient.Subscriptions().BySubscriptionId("subscription-id").Patch(context.Background(), requestBody, nil)


```