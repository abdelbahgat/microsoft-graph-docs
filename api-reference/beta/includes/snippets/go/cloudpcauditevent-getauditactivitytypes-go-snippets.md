---
description: "Automatically generated file. DO NOT MODIFY"
---

```go


import (
	  "context"
	  msgraphsdk "github.com/microsoftgraph/msgraph-beta-sdk-go"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)



getAuditActivityTypes, err := graphClient.DeviceManagement().VirtualEndpoint().AuditEvents().GetAuditActivityTypes().Get(context.Background(), nil)


```