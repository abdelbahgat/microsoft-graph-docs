---
description: "Automatically generated file. DO NOT MODIFY"
---

```go


import (
	  "context"
	  msgraphsdk "github.com/microsoftgraph/msgraph-beta-sdk-go"
	  graphcontacts "github.com/microsoftgraph/msgraph-beta-sdk-go/contacts"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)


requestParameters := &graphcontacts.ContactsDelta()RequestBuilderGetQueryParameters{
	Select: [] string {"displayName","jobTitle","mail"},
}
configuration := &graphcontacts.ContactsDelta()RequestBuilderGetRequestConfiguration{
	QueryParameters: requestParameters,
}

delta, err := graphClient.Contacts().Delta().Get(context.Background(), configuration)


```