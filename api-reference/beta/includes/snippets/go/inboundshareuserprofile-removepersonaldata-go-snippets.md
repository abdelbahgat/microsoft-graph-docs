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



graphClient.Directory().InboundSharedUserProfiles().ByInboundSharedUserProfileUserId("inboundSharedUserProfile-userId").RemovePersonalData().Post(context.Background(), nil)


```