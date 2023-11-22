---
description: "Automatically generated file. DO NOT MODIFY"
---

```go


import (
	  "context"
	  msgraphsdk "github.com/microsoftgraph/msgraph-sdk-go"
	  graphapplications(appid='{appid}') "github.com/microsoftgraph/msgraph-sdk-go/applications(appid='{appid}')"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)


requestParameters := &graphapplications(appid='{appid}').Applications(appId='{appId}')RequestBuilderGetQueryParameters{
	Select: [] string {"id","appId","displayName","requiredResourceAccess"},
}
configuration := &graphapplications(appid='{appid}').Applications(appId='{appId}')RequestBuilderGetRequestConfiguration{
	QueryParameters: requestParameters,
}

appId := "{appId}"
applications, err := graphClient.ApplicationsWithAppId(&appId).Get(context.Background(), configuration)


```