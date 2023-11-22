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



graphClient.Compliance().Ediscovery().Cases().ByCaseId("case-id").LegalHolds().ByLegalHoldId("legalHold-id").Delete(context.Background(), nil)


```