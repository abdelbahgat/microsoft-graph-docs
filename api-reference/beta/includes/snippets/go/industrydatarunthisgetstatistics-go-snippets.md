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



microsoftGraphIndustryDataGetStatistics, err := graphClient.External().IndustryData().Runs().ByIndustryDataRunId("industryDataRun-id").MicrosoftGraphIndustryDataGetStatistics().Get(context.Background(), nil)


```