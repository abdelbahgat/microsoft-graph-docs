---
description: "Automatically generated file. DO NOT MODIFY"
---

```go


import (
	  "context"
	  msgraphsdk "github.com/microsoftgraph/msgraph-sdk-go"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)



passiveDnsRecords, err := graphClient.Security().ThreatIntelligence().PassiveDnsRecords().ByPassiveDnsRecordId("passiveDnsRecord-id").Get(context.Background(), nil)


```