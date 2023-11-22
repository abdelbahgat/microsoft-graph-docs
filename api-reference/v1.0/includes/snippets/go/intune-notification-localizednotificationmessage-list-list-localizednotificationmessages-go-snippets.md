---
description: "Automatically generated file. DO NOT MODIFY"
---

```go


import (
	  "context"
	  msgraphsdk "github.com/microsoftgraph/msgraph-sdk-go"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)



localizedNotificationMessages, err := graphClient.DeviceManagement().NotificationMessageTemplates().ByNotificationMessageTemplateId("notificationMessageTemplate-id").LocalizedNotificationMessages().Get(context.Background(), nil)


```