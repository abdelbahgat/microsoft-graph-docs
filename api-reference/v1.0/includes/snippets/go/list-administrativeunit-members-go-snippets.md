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



members, err := graphClient.Directory().AdministrativeUnits().ByAdministrativeUnitId("administrativeUnit-id").Members().Get(context.Background(), nil)


```