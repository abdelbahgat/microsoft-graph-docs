---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
import (
	  "context"
	  msgraphsdk "github.com/microsoftgraph/msgraph-sdk-go"
	  graphmodels "github.com/microsoftgraph/msgraph-sdk-go/models"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)


requestBody := graphmodels.NewEvent()
subject := "Let's go for lunch"
requestBody.SetSubject(&subject) 
body := graphmodels.NewItemBody()
contentType := graphmodels.HTML_BODYTYPE 
body.SetContentType(&contentType) 
content := "Does mid month work for you?"
body.SetContent(&content) 
requestBody.SetBody(body)
start := graphmodels.NewDateTimeTimeZone()
dateTime := "2019-03-15T12:00:00"
start.SetDateTime(&dateTime) 
timeZone := "Pacific Standard Time"
start.SetTimeZone(&timeZone) 
requestBody.SetStart(start)
end := graphmodels.NewDateTimeTimeZone()
dateTime := "2019-03-15T14:00:00"
end.SetDateTime(&dateTime) 
timeZone := "Pacific Standard Time"
end.SetTimeZone(&timeZone) 
requestBody.SetEnd(end)
location := graphmodels.NewLocation()
displayName := "Harry's Bar"
location.SetDisplayName(&displayName) 
requestBody.SetLocation(location)


attendee := graphmodels.NewAttendee()
emailAddress := graphmodels.NewEmailAddress()
address := "adelev@contoso.onmicrosoft.com"
emailAddress.SetAddress(&address) 
name := "Adele Vance"
emailAddress.SetName(&name) 
attendee.SetEmailAddress(emailAddress)
type := graphmodels.REQUIRED_ATTENDEETYPE 
attendee.SetType(&type) 

attendees := []graphmodels.Objectable {
	attendee,

}
requestBody.SetAttendees(attendees)
transactionId := "7E163156-7762-4BEB-A1C6-729EA81755A7"
requestBody.SetTransactionId(&transactionId) 

result, err := graphClient.Me().Calendars().ByCalendarId("calendar-id").Events().Post(context.Background(), requestBody, nil)


```