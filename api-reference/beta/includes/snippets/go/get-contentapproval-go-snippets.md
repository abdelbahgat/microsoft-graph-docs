---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
import (
	  "context"
	  msgraphsdk "github.com/microsoftgraph/msgraph-beta-sdk-go"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)



result, err := graphClient.Admin().Windows().Updates().UpdatePolicies().ByUpdatePolicieId("updatePolicy-id").ComplianceChanges().ByComplianceChangeId("complianceChange-id").Get(context.Background(), nil)


```