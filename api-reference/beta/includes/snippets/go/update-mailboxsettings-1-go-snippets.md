---
description: "Automatically generated file. DO NOT MODIFY"
---

```go


import (
	  "context"
	  msgraphsdk "github.com/microsoftgraph/msgraph-beta-sdk-go"
	  graphmodels "github.com/microsoftgraph/msgraph-beta-sdk-go/models"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)


requestBody := graphmodels.NewMailboxSettings()
automaticRepliesSetting := graphmodels.NewAutomaticRepliesSetting()
status := graphmodels.SCHEDULED_AUTOMATICREPLIESSTATUS 
automaticRepliesSetting.SetStatus(&status) 
scheduledStartDateTime := graphmodels.NewDateTimeTimeZone()
dateTime := "2016-03-20T18:00:00.0000000"
scheduledStartDateTime.SetDateTime(&dateTime) 
timeZone := "UTC"
scheduledStartDateTime.SetTimeZone(&timeZone) 
automaticRepliesSetting.SetScheduledStartDateTime(scheduledStartDateTime)
scheduledEndDateTime := graphmodels.NewDateTimeTimeZone()
dateTime := "2016-03-28T18:00:00.0000000"
scheduledEndDateTime.SetDateTime(&dateTime) 
timeZone := "UTC"
scheduledEndDateTime.SetTimeZone(&timeZone) 
automaticRepliesSetting.SetScheduledEndDateTime(scheduledEndDateTime)
requestBody.SetAutomaticRepliesSetting(automaticRepliesSetting)
additionalData := map[string]interface{}{
	"odataContext" : "https://graph.microsoft.com/beta/$metadata#Me/mailboxSettings", 
}
requestBody.SetAdditionalData(additionalData)

mailboxSettings, err := graphClient.Me().MailboxSettings().Patch(context.Background(), requestBody, nil)


```