---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

headers := map[string]string{
	"Prefer": "outlook.timezone=\"Pacific Standard Time\"",
}
configuration := &graphconfig.EventsRequestBuilderPostRequestConfiguration{
	Headers: headers,
}
requestBody := graphmodels.NewEvent()
subject := "Let's go for lunch"
requestBody.SetSubject(&subject) 
body := graphmodels.NewItemBody()
contentType := graphmodels.HTML_BODYTYPE 
body.SetContentType(&contentType) 
content := "Does noon work for you?"
body.SetContent(&content) 
requestBody.SetBody(body)
start := graphmodels.NewDateTimeTimeZone()
dateTime := "2020-02-25T12:00:00"
start.SetDateTime(&dateTime) 
timeZone := "Pacific Standard Time"
start.SetTimeZone(&timeZone) 
requestBody.SetStart(start)
end := graphmodels.NewDateTimeTimeZone()
dateTime := "2020-02-25T14:00:00"
end.SetDateTime(&dateTime) 
timeZone := "Pacific Standard Time"
end.SetTimeZone(&timeZone) 
requestBody.SetEnd(end)
location := graphmodels.NewLocation()
displayName := "Harry's Bar"
location.SetDisplayName(&displayName) 
requestBody.SetLocation(location)


 := graphmodels.New()
additionalData := map[string]interface{}{
emailAddress := graphmodels.New()
address := "AlexW@contoso.OnMicrosoft.com"
emailAddress.SetAddress(&address) 
name := "Alex Wilbur"
emailAddress.SetName(&name) 
	.SetEmailAddress(emailAddress)
	"type" : "required", 
}
.SetAdditionalData(additionalData)

attendees := []graphmodels.Objectable {
	,

}
requestBody.SetAttendees(attendees)
recurrence := graphmodels.NewPatternedRecurrence()
pattern := graphmodels.NewRecurrencePattern()
type := graphmodels.DAILY_RECURRENCEPATTERNTYPE 
pattern.SetType(&type) 
interval := int32(1)
pattern.SetInterval(&interval) 
recurrence.SetPattern(pattern)
range := graphmodels.NewRecurrenceRange()
type := graphmodels.NUMBERED_RECURRENCERANGETYPE 
range.SetType(&type) 
startDate := "2020-02-25"
range.SetStartDate(&startDate) 
numberOfOccurrences := int32(2)
range.SetNumberOfOccurrences(&numberOfOccurrences) 
recurrence.SetRange(range)
requestBody.SetRecurrence(recurrence)

result, err := graphClient.Me().Events().PostWithRequestConfigurationAndResponseHandler(requestBody, configuration, nil)


```