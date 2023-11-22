---
description: "Automatically generated file. DO NOT MODIFY"
---

```go


import (
	  "context"
	  msgraphsdk "github.com/microsoftgraph/msgraph-sdk-go"
	  graphdirectory "github.com/microsoftgraph/msgraph-sdk-go/directory"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)


requestParameters := &graphdirectory.DirectoryAttributeSetsRequestBuilderGetQueryParameters{
	Orderby: [] string {"id"},
}
configuration := &graphdirectory.DirectoryAttributeSetsRequestBuilderGetRequestConfiguration{
	QueryParameters: requestParameters,
}

attributeSets, err := graphClient.Directory().AttributeSets().Get(context.Background(), configuration)


```