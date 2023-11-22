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


requestBody := graphmodels.NewChannel()
displayName := "Architecture Discussion"
requestBody.SetDisplayName(&displayName) 
description := "This channel is where we debate all future architecture plans"
requestBody.SetDescription(&description) 
membershipType := graphmodels.STANDARD_CHANNELMEMBERSHIPTYPE 
requestBody.SetMembershipType(&membershipType) 

channels, err := graphClient.Teams().ByTeamId("team-id").Channels().Post(context.Background(), requestBody, nil)


```