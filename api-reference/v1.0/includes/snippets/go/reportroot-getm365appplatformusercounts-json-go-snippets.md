---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
import (
	  "context"
	  msgraphsdk "github.com/microsoftgraph/msgraph-sdk-go"
	  graphconfig "github.com/microsoftgraph/msgraph-sdk-go/reports"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)



requestFormat := "application/json"

requestParameters := &graphconfig.ReportsGetM365AppPlatformUserCounts(period='{period}')RequestBuilderGetQueryParameters{
	Format: &requestFormat,
}
configuration := &graphconfig.ReportsGetM365AppPlatformUserCounts(period='{period}')RequestBuilderGetRequestConfiguration{
	QueryParameters: requestParameters,
}

graphClient.Reports().GetM365AppPlatformUserCounts(period='{period}')().Get(context.Background(), configuration)


```