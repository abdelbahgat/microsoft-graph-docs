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



indicators, err := graphClient.Security().ThreatIntelligence().IntelProfiles().ByIntelligenceProfileId("intelligenceProfile-id").Indicators().Get(context.Background(), nil)


```