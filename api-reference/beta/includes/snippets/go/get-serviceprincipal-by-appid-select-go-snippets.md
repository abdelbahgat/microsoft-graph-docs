---
description: "Automatically generated file. DO NOT MODIFY"
---

```go


import (
	  "context"
	  msgraphsdk "github.com/microsoftgraph/msgraph-beta-sdk-go"
	  graphserviceprincipals(appid='{appid}') "github.com/microsoftgraph/msgraph-beta-sdk-go/serviceprincipals(appid='{appid}')"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)


requestParameters := &graphserviceprincipals(appid='{appid}').ServicePrincipals(appId='{appId}')RequestBuilderGetQueryParameters{
	Select: [] string {"id","appId","displayName","appRoles","publishedPermissionScopes","resourceSpecificApplicationPermissions"},
}
configuration := &graphserviceprincipals(appid='{appid}').ServicePrincipals(appId='{appId}')RequestBuilderGetRequestConfiguration{
	QueryParameters: requestParameters,
}

appId := "{appId}"
servicePrincipals, err := graphClient.ServicePrincipalsWithAppId(&appId).Get(context.Background(), configuration)


```