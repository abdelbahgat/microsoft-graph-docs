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
subject := "Plan summer company picnic"
requestBody.SetSubject(&subject) 
body := graphmodels.NewItemBody()
contentType := graphmodels.HTML_BODYTYPE 
body.SetContentType(&contentType) 
content := "Let's kick-start this event planning!"
body.SetContent(&content) 
requestBody.SetBody(body)
start := graphmodels.NewDateTimeTimeZone()
dateTime := "2017-08-30T11:00:00"
start.SetDateTime(&dateTime) 
timeZone := "Pacific Standard Time"
start.SetTimeZone(&timeZone) 
requestBody.SetStart(start)
end := graphmodels.NewDateTimeTimeZone()
dateTime := "2017-08-30T12:00:00"
end.SetDateTime(&dateTime) 
timeZone := "Pacific Standard Time"
end.SetTimeZone(&timeZone) 
requestBody.SetEnd(end)


 := graphmodels.New()
additionalData := map[string]interface{}{
emailAddress := graphmodels.New()
address := "DanaS@contoso.onmicrosoft.com"
emailAddress.SetAddress(&address) 
name := "Dana Swope"
emailAddress.SetName(&name) 
	.SetEmailAddress(emailAddress)
	"type" : "Required", 
}
.SetAdditionalData(additionalData)
 := graphmodels.New()
additionalData := map[string]interface{}{
emailAddress := graphmodels.New()
address := "AlexW@contoso.onmicrosoft.com"
emailAddress.SetAddress(&address) 
name := "Alex Wilber"
emailAddress.SetName(&name) 
	.SetEmailAddress(emailAddress)
	"type" : "Required", 
}
.SetAdditionalData(additionalData)

attendees := []graphmodels.Objectable {
	,
	,

}
requestBody.SetAttendees(attendees)
location := graphmodels.NewLocation()
displayName := "Conf Room 3; Fourth Coffee; Home Office"
location.SetDisplayName(&displayName) 
locationType := graphmodels.DEFAULT_LOCATIONTYPE 
location.SetLocationType(&locationType) 
requestBody.SetLocation(location)


location := graphmodels.NewLocation()
displayName := "Conf Room 3"
location.SetDisplayName(&displayName) 
location1 := graphmodels.NewLocation()
displayName := "Fourth Coffee"
location1.SetDisplayName(&displayName) 
address := graphmodels.NewPhysicalAddress()
street := "4567 Main St"
address.SetStreet(&street) 
city := "Redmond"
address.SetCity(&city) 
state := "WA"
address.SetState(&state) 
countryOrRegion := "US"
address.SetCountryOrRegion(&countryOrRegion) 
postalCode := "32008"
address.SetPostalCode(&postalCode) 
location1.SetAddress(address)
coordinates := graphmodels.NewOutlookGeoCoordinates()
latitude := float64(47.672)
coordinates.SetLatitude(&latitude) 
longitude := float64(-102.103)
coordinates.SetLongitude(&longitude) 
location1.SetCoordinates(coordinates)
location2 := graphmodels.NewLocation()
displayName := "Home Office"
location2.SetDisplayName(&displayName) 

locations := []graphmodels.Locationable {
	location,
	location1,
	location2,

}
requestBody.SetLocations(locations)
allowNewTimeProposals := true
requestBody.SetAllowNewTimeProposals(&allowNewTimeProposals) 

result, err := graphClient.Me().Events().PostWithRequestConfigurationAndResponseHandler(requestBody, configuration, nil)


```