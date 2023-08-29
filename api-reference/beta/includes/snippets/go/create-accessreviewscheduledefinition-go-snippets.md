---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewAccessReviewScheduleDefinition()
displayName := "Test create"
requestBody.SetDisplayName(&displayName) 
descriptionForAdmins := "New scheduled access review"
requestBody.SetDescriptionForAdmins(&descriptionForAdmins) 
descriptionForReviewers := "If you have any questions, contact jerry@contoso.com"
requestBody.SetDescriptionForReviewers(&descriptionForReviewers) 
scope := graphmodels.NewAccessReviewScope()
"@odata.type" := "#microsoft.graph.accessReviewQueryScope"
scope.Set"@odata.type"(&"@odata.type") 
additionalData := map[string]interface{}{
	"query" : "/groups/02f3bafb-448c-487c-88c2-5fd65ce49a41/transitiveMembers", 
	"queryType" : "MicrosoftGraph", 
}
scope.SetAdditionalData(additionalData)
requestBody.SetScope(scope)


 := graphmodels.New()
additionalData := map[string]interface{}{
	"query" : "/users/398164b1-5196-49dd-ada2-364b49f99b27", 
	"queryType" : "MicrosoftGraph", 
}
.SetAdditionalData(additionalData)

reviewers := []graphmodels.Objectable {
	,

}
requestBody.SetReviewers(reviewers)
settings := graphmodels.NewAccessReviewScheduleSettings()
mailNotificationsEnabled := true
settings.SetMailNotificationsEnabled(&mailNotificationsEnabled) 
reminderNotificationsEnabled := true
settings.SetReminderNotificationsEnabled(&reminderNotificationsEnabled) 
justificationRequiredOnApproval := true
settings.SetJustificationRequiredOnApproval(&justificationRequiredOnApproval) 
defaultDecisionEnabled := false
settings.SetDefaultDecisionEnabled(&defaultDecisionEnabled) 
defaultDecision := "None"
settings.SetDefaultDecision(&defaultDecision) 
instanceDurationInDays := int32(1)
settings.SetInstanceDurationInDays(&instanceDurationInDays) 
recommendationsEnabled := true
settings.SetRecommendationsEnabled(&recommendationsEnabled) 
recurrence := graphmodels.NewPatternedRecurrence()
pattern := graphmodels.NewRecurrencePattern()
type := graphmodels.WEEKLY_RECURRENCEPATTERNTYPE 
pattern.SetType(&type) 
interval := int32(1)
pattern.SetInterval(&interval) 
recurrence.SetPattern(pattern)
range := graphmodels.NewRecurrenceRange()
type := graphmodels.NOEND_RECURRENCERANGETYPE 
range.SetType(&type) 
startDate := "2020-09-08T12:02:30.667Z"
range.SetStartDate(&startDate) 
recurrence.SetRange(range)
settings.SetRecurrence(recurrence)
requestBody.SetSettings(settings)

result, err := graphClient.IdentityGovernance().AccessReviews().Definitions().Post(requestBody)


```