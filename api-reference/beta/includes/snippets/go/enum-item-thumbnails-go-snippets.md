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



thumbnails, err := graphClient.Drives().ByDriveId("drive-id").Items().ByDriveItemId("driveItem-id").Thumbnails().Get(context.Background(), nil)


```