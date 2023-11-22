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


requestBody := graphmodels.NewTeam()
additionalData := map[string]interface{}{
	"odataBind" : "https://graph.microsoft.com/v1.0/teamsTemplates('standard')", 
	"odataBind" : "https://graph.microsoft.com/v1.0/groups('71392b2f-1765-406e-86af-5907d9bdb2ab')", 
}
requestBody.SetAdditionalData(additionalData)

teams, err := graphClient.Teams().Post(context.Background(), requestBody, nil)


```