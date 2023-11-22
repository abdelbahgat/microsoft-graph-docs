---
description: "Automatically generated file. DO NOT MODIFY"
---

```go


import (
	  "context"
	  msgraphsdk "github.com/microsoftgraph/msgraph-beta-sdk-go"
	  graphsecurity "github.com/microsoftgraph/msgraph-beta-sdk-go/security"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)


requestBody := graphsecurity.NewUpdateIndexPostRequestBody()
ids := []string {
	"7f697316-43ed-48e1-977f-261be050db93",
	"b26888b3-e1f5-47c5-bdf2-33d1b90cb2e8",
}
requestBody.SetIds(ids)

graphClient.Security().Cases().EdiscoveryCases().ByEdiscoveryCaseId("ediscoveryCase-id").Custodians().MicrosoftGraphSecurityUpdateIndex().Post(context.Background(), requestBody, nil)


```