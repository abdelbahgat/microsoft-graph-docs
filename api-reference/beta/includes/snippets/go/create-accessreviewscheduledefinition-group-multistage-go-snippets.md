---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewAccessReviewScheduleDefinition()
displayName := "Group Multi-stage Access Review"
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


accessReviewStageSettings := graphmodels.NewAccessReviewStageSettings()
stageId := "1"
accessReviewStageSettings.SetStageId(&stageId) 
durationInDays := int32(2)
accessReviewStageSettings.SetDurationInDays(&durationInDays) 
recommendationsEnabled := false
accessReviewStageSettings.SetRecommendationsEnabled(&recommendationsEnabled) 
decisionsThatWillMoveToNextStage := []String {
	"NotReviewed",
	"Approve",

}
accessReviewStageSettings.SetDecisionsThatWillMoveToNextStage(decisionsThatWillMoveToNextStage)


 := graphmodels.New()
additionalData := map[string]interface{}{
	"query" : "/users/398164b1-5196-49dd-ada2-364b49f99b27", 
	"queryType" : "MicrosoftGraph", 
}
.SetAdditionalData(additionalData)

reviewers := []graphmodels.Objectable {
	,

}
accessReviewStageSettings.SetReviewers(reviewers)
accessReviewStageSettings1 := graphmodels.NewAccessReviewStageSettings()
stageId := "2"
accessReviewStageSettings1.SetStageId(&stageId) 
dependsOn := []String {
	"1",

}
accessReviewStageSettings1.SetDependsOn(dependsOn)
durationInDays := int32(2)
accessReviewStageSettings1.SetDurationInDays(&durationInDays) 
recommendationsEnabled := true
accessReviewStageSettings1.SetRecommendationsEnabled(&recommendationsEnabled) 


 := graphmodels.New()
additionalData := map[string]interface{}{
	"query" : "./manager", 
	"queryType" : "MicrosoftGraph", 
	"queryRoot" : "decisions", 
}
.SetAdditionalData(additionalData)

reviewers := []graphmodels.Objectable {
	,

}
accessReviewStageSettings1.SetReviewers(reviewers)


 := graphmodels.New()
additionalData := map[string]interface{}{
	"query" : "/groups/072ac5f4-3f13-4088-ab30-0a276f3e6322/transitiveMembers", 
	"queryType" : "MicrosoftGraph", 
}
.SetAdditionalData(additionalData)

fallbackReviewers := []graphmodels.Objectable {
	,

}
accessReviewStageSettings1.SetFallbackReviewers(fallbackReviewers)

stageSettings := []graphmodels.AccessReviewStageSettingsable {
	accessReviewStageSettings,
	accessReviewStageSettings1,

}
requestBody.SetStageSettings(stageSettings)
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
instanceDurationInDays := int32(4)
settings.SetInstanceDurationInDays(&instanceDurationInDays) 
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
decisionHistoriesForReviewersEnabled := true
settings.SetDecisionHistoriesForReviewersEnabled(&decisionHistoriesForReviewersEnabled) 
requestBody.SetSettings(settings)

result, err := graphClient.IdentityGovernance().AccessReviews().Definitions().Post(requestBody)


```