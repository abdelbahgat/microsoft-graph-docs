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



directoryAudits, err := graphClient.AuditLogs().DirectoryAudits().ByDirectoryAuditId("directoryAudit-id").Get(context.Background(), nil)


```