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


requestBody := graphmodels.NewEducationalActivity()
institution := graphmodels.NewInstitutionData()
location := graphmodels.NewPhysicalAddress()
type := graphmodels.BUSINESS_PHYSICALADDRESSTYPE 
location.SetType(&type) 
postOfficeBox := null
location.SetPostOfficeBox(&postOfficeBox) 
street := "12000 E Prospect Rd"
location.SetStreet(&street) 
city := "Fort Collins"
location.SetCity(&city) 
state := "Colorado"
location.SetState(&state) 
countryOrRegion := "USA"
location.SetCountryOrRegion(&countryOrRegion) 
postalCode := "80525"
location.SetPostalCode(&postalCode) 
institution.SetLocation(location)
requestBody.SetInstitution(institution)

educationalActivities, err := graphClient.Me().Profile().EducationalActivities().ByEducationalActivityId("educationalActivity-id").Patch(context.Background(), requestBody, nil)


```