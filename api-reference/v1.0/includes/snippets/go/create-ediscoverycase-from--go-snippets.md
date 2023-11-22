---
description: "Automatically generated file. DO NOT MODIFY"
---

```go


import (
	  "context"
	  msgraphsdk "github.com/microsoftgraph/msgraph-sdk-go"
	  graphmodelssecurity "github.com/microsoftgraph/msgraph-sdk-go/models/security"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)


requestBody := graphmodelssecurity.NewEdiscoveryCase()
displayName := "CONTOSO LITIGATION-005"
requestBody.SetDisplayName(&displayName) 
description := "Project Bazooka"
requestBody.SetDescription(&description) 
externalId := "324516"
requestBody.SetExternalId(&externalId) 

ediscoveryCases, err := graphClient.Security().Cases().EdiscoveryCases().Post(context.Background(), requestBody, nil)


```