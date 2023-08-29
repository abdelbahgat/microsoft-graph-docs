---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewAccessReviewScheduleDefinition()
displayName := "Review employee access to LinkedIn"
requestBody.SetDisplayName(&displayName) 
descriptionForAdmins := "Review employee access to LinkedIn"
requestBody.SetDescriptionForAdmins(&descriptionForAdmins) 
scope := graphmodels.NewAccessReviewScope()
"@odata.type" := "#microsoft.graph.principalResourceMembershipsScope"
scope.Set"@odata.type"(&"@odata.type") 
additionalData := map[string]interface{}{


 := graphmodels.New()
"@odata.type" := "#microsoft.graph.accessReviewQueryScope"
.Set"@odata.type"(&"@odata.type") 
query := "/users"
.SetQuery(&query) 
queryType := "MicrosoftGraph"
.SetQueryType(&queryType) 

	principalScopes := []graphmodels.Objectable {
		,

	}


 := graphmodels.New()
"@odata.type" := "#microsoft.graph.accessReviewQueryScope"
.Set"@odata.type"(&"@odata.type") 
query := "/servicePrincipals/bae11f90-7d5d-46ba-9f55-8112b59d92ae"
.SetQuery(&query) 
queryType := "MicrosoftGraph"
.SetQueryType(&queryType) 

	resourceScopes := []graphmodels.Objectable {
		,

	}
}
scope.SetAdditionalData(additionalData)
requestBody.SetScope(scope)


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
requestBody.SetReviewers(reviewers)


 := graphmodels.New()
additionalData := map[string]interface{}{
	"query" : "/groups/072ac5f4-3f13-4088-ab30-0a276f3e6322/transitiveMembers", 
	"queryType" : "MicrosoftGraph", 
}
.SetAdditionalData(additionalData)

backupReviewers := []graphmodels.Objectable {
	,

}
requestBody.SetBackupReviewers(backupReviewers)


 := graphmodels.New()
additionalData := map[string]interface{}{
	"query" : "/groups/072ac5f4-3f13-4088-ab30-0a276f3e6322/transitiveMembers", 
	"queryType" : "MicrosoftGraph", 
}
.SetAdditionalData(additionalData)

fallbackReviewers := []graphmodels.Objectable {
	,

}
requestBody.SetFallbackReviewers(fallbackReviewers)
settings := graphmodels.NewAccessReviewScheduleSettings()
mailNotificationsEnabled := true
settings.SetMailNotificationsEnabled(&mailNotificationsEnabled) 
reminderNotificationsEnabled := true
settings.SetReminderNotificationsEnabled(&reminderNotificationsEnabled) 
justificationRequiredOnApproval := true
settings.SetJustificationRequiredOnApproval(&justificationRequiredOnApproval) 
defaultDecisionEnabled := true
settings.SetDefaultDecisionEnabled(&defaultDecisionEnabled) 
defaultDecision := "Recommendation"
settings.SetDefaultDecision(&defaultDecision) 
instanceDurationInDays := int32(180)
settings.SetInstanceDurationInDays(&instanceDurationInDays) 
autoApplyDecisionsEnabled := true
settings.SetAutoApplyDecisionsEnabled(&autoApplyDecisionsEnabled) 
recommendationsEnabled := true
settings.SetRecommendationsEnabled(&recommendationsEnabled) 
recurrence := graphmodels.NewPatternedRecurrence()
pattern := graphmodels.NewRecurrencePattern()
type := graphmodels.ABSOLUTEMONTHLY_RECURRENCEPATTERNTYPE 
pattern.SetType(&type) 
interval := int32(6)
pattern.SetInterval(&interval) 
dayOfMonth := int32(0)
pattern.SetDayOfMonth(&dayOfMonth) 
recurrence.SetPattern(pattern)
range := graphmodels.NewRecurrenceRange()
type := graphmodels.NUMBERED_RECURRENCERANGETYPE 
range.SetType(&type) 
startDate := "2021-05-05"
range.SetStartDate(&startDate) 
endDate := "2022-05-05"
range.SetEndDate(&endDate) 
recurrence.SetRange(range)
settings.SetRecurrence(recurrence)
requestBody.SetSettings(settings)

result, err := graphClient.IdentityGovernance().AccessReviews().Definitions().Post(requestBody)


```