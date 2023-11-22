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



sensitivityLabels, err := graphClient.Users().ByUserId("user-id").Security().InformationProtection().SensitivityLabels().Get(context.Background(), nil)


```