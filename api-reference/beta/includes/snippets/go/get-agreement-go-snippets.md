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



agreements, err := graphClient.IdentityGovernance().TermsOfUse().Agreements().ByAgreementId("agreement-id").Get(context.Background(), nil)


```