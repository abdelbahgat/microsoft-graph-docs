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



graphClient.DeviceManagement().MobileThreatDefenseConnectors().ByMobileThreatDefenseConnectorId("mobileThreatDefenseConnector-id").Delete(context.Background(), nil)


```