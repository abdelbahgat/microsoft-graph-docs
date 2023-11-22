---
description: "Automatically generated file. DO NOT MODIFY"
---

```go


import (
	  "context"
	  msgraphsdk "github.com/microsoftgraph/msgraph-sdk-go"
	  graphmodels "github.com/microsoftgraph/msgraph-sdk-go/models"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)


requestBody := graphmodels.NewAllowedValue()
isActive := false
requestBody.SetIsActive(&isActive) 

allowedValues, err := graphClient.Directory().CustomSecurityAttributeDefinitions().ByCustomSecurityAttributeDefinitionId("customSecurityAttributeDefinition-id").AllowedValues().ByAllowedValueId("allowedValue-id").Patch(context.Background(), requestBody, nil)


```