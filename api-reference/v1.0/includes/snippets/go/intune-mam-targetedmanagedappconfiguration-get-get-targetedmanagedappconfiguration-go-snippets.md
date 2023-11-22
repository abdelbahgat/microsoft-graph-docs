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



targetedManagedAppConfigurations, err := graphClient.DeviceAppManagement().TargetedManagedAppConfigurations().ByTargetedManagedAppConfigurationId("targetedManagedAppConfiguration-id").Get(context.Background(), nil)


```