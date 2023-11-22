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



intelligenceProfileIndicators, err := graphClient.Security().ThreatIntelligence().IntelligenceProfileIndicators().ByIntelligenceProfileIndicatorId("intelligenceProfileIndicator-id").Get(context.Background(), nil)


```