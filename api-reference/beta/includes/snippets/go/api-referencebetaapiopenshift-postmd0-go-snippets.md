---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

headers := map[string]string{
	"Authorization": "Bearer {token}",
}
configuration := &graphconfig.OpenShiftsRequestBuilderPostRequestConfiguration{
	Headers: headers,
}
requestBody := graphmodels.NewOpenShift()
id := "OPNSHFT_577b75d2-a927-48c0-a5d1-dc984894e7b8"
requestBody.SetId(&id) 
schedulingGroupId := "TAG_228940ed-ff84-4e25-b129-1b395cf78be0"
requestBody.SetSchedulingGroupId(&schedulingGroupId) 
sharedOpenShift := graphmodels.NewsharedOpenShift()
notes := "InventoryManagement"
sharedOpenShift.SetNotes(&notes) 
openSlotCount := int32(2)
sharedOpenShift.SetOpenSlotCount(&openSlotCount) 
displayName := "Dayshift"
sharedOpenShift.SetDisplayName(&displayName) 
startDateTime , err := time.Parse(time.RFC3339, "2018-10-04T00: 58: 45.340Z")
sharedOpenShift.SetStartDateTime(&startDateTime) 
endDateTime , err := time.Parse(time.RFC3339, "2018-10-04T09: 50: 45.332Z")
sharedOpenShift.SetEndDateTime(&endDateTime) 
theme := graphmodels.WHITE_SCHEDULEENTITYTHEME 
sharedOpenShift.SetTheme(&theme) 


shiftActivity := graphmodels.NewShiftActivity()
isPaid := true
shiftActivity.SetIsPaid(&isPaid) 
startDateTime , err := time.Parse(time.RFC3339, "2018-10-04T00: 58: 45.340Z")
shiftActivity.SetStartDateTime(&startDateTime) 
endDateTime , err := time.Parse(time.RFC3339, "2018-10-04T01: 58: 45.340Z")
shiftActivity.SetEndDateTime(&endDateTime) 
code := ""
shiftActivity.SetCode(&code) 
displayName := "Lunch"
shiftActivity.SetDisplayName(&displayName) 

activities := []graphmodels.ShiftActivityable {
	shiftActivity,

}
sharedOpenShift.SetActivities(activities)
requestBody.SetSharedOpenShift(sharedOpenShift)
draftOpenShift := null
requestBody.SetDraftOpenShift(&draftOpenShift) 
createdDateTime , err := time.Parse(time.RFC3339, "2019-03-14T04: 32: 51.451Z")
requestBody.SetCreatedDateTime(&createdDateTime) 
lastModifiedDateTime , err := time.Parse(time.RFC3339, "2019-03-14T05: 32: 51.451Z")
requestBody.SetLastModifiedDateTime(&lastModifiedDateTime) 
lastModifiedBy := graphmodels.NewIdentitySet()
application := null
lastModifiedBy.SetApplication(&application) 
device := null
lastModifiedBy.SetDevice(&device) 
user := graphmodels.NewIdentity()
id := "366c0b19-49b1-41b5-a03f-9f3887bd0ed8"
user.SetId(&id) 
displayName := "JohnDoe"
user.SetDisplayName(&displayName) 
lastModifiedBy.SetUser(user)
additionalData := map[string]interface{}{
	conversation := null
lastModifiedBy.SetConversation(&conversation) 
}
lastModifiedBy.SetAdditionalData(additionalData)
requestBody.SetLastModifiedBy(lastModifiedBy)

result, err := graphClient.TeamsById("team-id").Schedule().OpenShifts().PostWithRequestConfigurationAndResponseHandler(requestBody, configuration, nil)


```