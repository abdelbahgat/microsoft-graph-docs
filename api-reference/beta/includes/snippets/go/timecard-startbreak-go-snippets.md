---
description: "Automatically generated file. DO NOT MODIFY"
---

```go


import (
	  "context"
	  msgraphsdk "github.com/microsoftgraph/msgraph-beta-sdk-go"
	  graphteams "github.com/microsoftgraph/msgraph-beta-sdk-go/teams"
	  graphmodels "github.com/microsoftgraph/msgraph-beta-sdk-go/models"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)


requestBody := graphteams.NewStartBreakPostRequestBody()
notes := graphmodels.NewItemBody()
contentType := graphmodels.TEXT_BODYTYPE 
notes.SetContentType(&contentType) 
content := "start break smaple notes"
notes.SetContent(&content) 
requestBody.SetNotes(notes)
additionalData := map[string]interface{}{
	atAprovedLocation := true
requestBody.SetAtAprovedLocation(&atAprovedLocation) 
}
requestBody.SetAdditionalData(additionalData)

startBreak, err := graphClient.Teams().ByTeamId("team-id").Schedule().TimeCards().ByTimeCardId("timeCard-id").StartBreak().Post(context.Background(), requestBody, nil)


```