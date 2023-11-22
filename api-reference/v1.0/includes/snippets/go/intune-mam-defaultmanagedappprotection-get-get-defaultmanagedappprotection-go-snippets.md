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



defaultManagedAppProtections, err := graphClient.DeviceAppManagement().DefaultManagedAppProtections().ByDefaultManagedAppProtectionId("defaultManagedAppProtection-id").Get(context.Background(), nil)


```