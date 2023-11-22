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


requestBody := graphmodels.NewMailboxSettings()
delegateMeetingMessageDeliveryOptions := graphmodels.SENDTODELEGATEANDPRINCIPAL_DELEGATEMEETINGMESSAGEDELIVERYOPTIONS 
requestBody.SetDelegateMeetingMessageDeliveryOptions(&delegateMeetingMessageDeliveryOptions) 

mailboxSettings, err := graphClient.Users().ByUserId("user-id").MailboxSettings().Patch(context.Background(), requestBody, nil)


```