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



analytics, err := graphClient.Drives().ByDriveId("drive-id").Items().ByDriveItemId("driveItem-id").Analytics().Get(context.Background(), nil)


```