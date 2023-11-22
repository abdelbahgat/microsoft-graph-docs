---
description: "Automatically generated file. DO NOT MODIFY"
---

```go


import (
	  "context"
	  msgraphsdk "github.com/microsoftgraph/msgraph-beta-sdk-go"
	  graphmodelsediscovery "github.com/microsoftgraph/msgraph-beta-sdk-go/models/ediscovery"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)


requestBody := graphmodelsediscovery.NewUnifiedGroupSource()
includedSources := graphmodels.MAILBOX, SITE_SOURCETYPE 
requestBody.SetIncludedSources(&includedSources) 
additionalData := map[string]interface{}{
	"odataBind" : "https://graph.microsoft.com/v1.0/groups/b96f95c5-b1b3-4142-b039-8ac79e7d2c84", 
}
requestBody.SetAdditionalData(additionalData)

unifiedGroupSources, err := graphClient.Compliance().Ediscovery().Cases().ByCaseId("case-id").Custodians().ByCustodianId("custodian-id").UnifiedGroupSources().Post(context.Background(), requestBody, nil)


```