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



graphClient.Print().PrinterShares().ByPrinterShareId("printerShare-id").AllowedUsers().ByUserId("user-id").Ref().Delete(context.Background(), nil)


```