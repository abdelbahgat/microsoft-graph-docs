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



snapshots, err := graphClient.DeviceManagement().VirtualEndpoint().Snapshots().ByCloudPcSnapshotId("cloudPcSnapshot-id").Get(context.Background(), nil)


```