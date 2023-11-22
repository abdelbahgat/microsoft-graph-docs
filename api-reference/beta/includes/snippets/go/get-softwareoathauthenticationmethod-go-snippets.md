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



softwareOathMethods, err := graphClient.Me().Authentication().SoftwareOathMethods().BySoftwareOathAuthenticationMethodId("softwareOathAuthenticationMethod-id").Get(context.Background(), nil)


```