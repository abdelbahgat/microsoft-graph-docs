---
description: "Automatically generated file. DO NOT MODIFY"
---

```go


import (
	  "context"
	  msgraphsdk "github.com/microsoftgraph/msgraph-beta-sdk-go"
	  graphreports "github.com/microsoftgraph/msgraph-beta-sdk-go/reports"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)



requestFilter := "appId eq 'f4d9654f-0305-4072-878c-8bf266dfe146'"

requestParameters := &graphreports.ReportsAppCredentialSignInActivitiesRequestBuilderGetQueryParameters{
	Filter: &requestFilter,
}
configuration := &graphreports.ReportsAppCredentialSignInActivitiesRequestBuilderGetRequestConfiguration{
	QueryParameters: requestParameters,
}

appCredentialSignInActivities, err := graphClient.Reports().AppCredentialSignInActivities().Get(context.Background(), configuration)


```