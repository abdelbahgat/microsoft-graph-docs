---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
import (
	  "context"
	  msgraphsdk "github.com/microsoftgraph/msgraph-beta-sdk-go"
	  graphmodels "github.com/microsoftgraph/msgraph-beta-sdk-go/Teams/Item/Schedule/TimeCards/Item/ClockOut"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)


requestBody := graphmodels.NewClockOutPostRequestBody()
notes := graphmodels.NewItemBody()
contentType := graphmodels.TEXT_BODYTYPE 
notes.SetContentType(&contentType) 
content := "clock out smaple notes"
notes.SetContent(&content) 
requestBody.SetNotes(notes)
additionalData := map[string]interface{}{
	atAprovedLocation := true
requestBody.SetAtAprovedLocation(&atAprovedLocation) 
}
requestBody.SetAdditionalData(additionalData)

result, err := graphClient.Teams().ByTeamId("team-id").Schedule().TimeCards().ByTimeCardId("timeCard-id").ClockOut().Post(context.Background(), requestBody, nil)


```