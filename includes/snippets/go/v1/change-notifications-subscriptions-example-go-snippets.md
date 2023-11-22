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
changeType := "created,updated"
requestBody.SetChangeType(&changeType) 
notificationUrl := "https://webhook.azurewebsites.net/notificationClient"
requestBody.SetNotificationUrl(&notificationUrl) 
lifecycleNotificationUrl := "https://webhook.azurewebsites.net/api/lifecycleNotifications"
requestBody.SetLifecycleNotificationUrl(&lifecycleNotificationUrl) 
resource := "/me/mailfolders('inbox')/messages"
requestBody.SetResource(&resource) 
expirationDateTime , err := time.Parse(time.RFC3339, "2016-03-20T11:00:00.0000000Z")
requestBody.SetExpirationDateTime(&expirationDateTime) 
clientState := "SecretClientState"
requestBody.SetClientState(&clientState) 

subscriptions, err := graphClient.Subscriptions().Post(context.Background(), requestBody, nil)


```