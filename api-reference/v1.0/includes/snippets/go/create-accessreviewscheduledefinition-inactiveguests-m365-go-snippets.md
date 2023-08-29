---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewAccessReviewScheduleDefinition()
displayName := "Review inactive guests on teams"
requestBody.SetDisplayName(&displayName) 
descriptionForAdmins := "Control guest user access to our teams."
requestBody.SetDescriptionForAdmins(&descriptionForAdmins) 
descriptionForReviewers := "Information security is everyone's responsibility. Review our access policy for more."
requestBody.SetDescriptionForReviewers(&descriptionForReviewers) 
instanceEnumerationScope := graphmodels.NewAccessReviewScope()
"@odata.type" := "#microsoft.graph.accessReviewQueryScope"
instanceEnumerationScope.Set"@odata.type"(&"@odata.type") 
additionalData := map[string]interface{}{
	"query" : "/groups?$filter=(groupTypes/any(c:c+eq+'Unified') and resourceProvisioningOptions/Any(x:x eq 'Team')')", 
	"queryType" : "MicrosoftGraph", 
}
instanceEnumerationScope.SetAdditionalData(additionalData)
requestBody.SetInstanceEnumerationScope(instanceEnumerationScope)
scope := graphmodels.NewAccessReviewScope()
"@odata.type" := "#microsoft.graph.accessReviewInactiveUsersQueryScope"
scope.Set"@odata.type"(&"@odata.type") 
additionalData := map[string]interface{}{
	"query" : "./members/microsoft.graph.user/?$filter=(userType eq 'Guest')", 
	"queryType" : "MicrosoftGraph", 
	"inactiveDuration" : "P30D", 
}
scope.SetAdditionalData(additionalData)
requestBody.SetScope(scope)


accessReviewReviewerScope := graphmodels.NewAccessReviewReviewerScope()
query := "./owners"
accessReviewReviewerScope.SetQuery(&query) 
queryType := "MicrosoftGraph"
accessReviewReviewerScope.SetQueryType(&queryType) 

reviewers := []graphmodels.AccessReviewReviewerScopeable {
	accessReviewReviewerScope,

}
requestBody.SetReviewers(reviewers)


accessReviewReviewerScope := graphmodels.NewAccessReviewReviewerScope()
query := "/users/fc9a2c2b-1ddc-486d-a211-5fe8ca77fa1f"
accessReviewReviewerScope.SetQuery(&query) 
queryType := "MicrosoftGraph"
accessReviewReviewerScope.SetQueryType(&queryType) 

fallbackReviewers := []graphmodels.AccessReviewReviewerScopeable {
	accessReviewReviewerScope,

}
requestBody.SetFallbackReviewers(fallbackReviewers)
settings := graphmodels.NewAccessReviewScheduleSettings()
mailNotificationsEnabled := true
settings.SetMailNotificationsEnabled(&mailNotificationsEnabled) 
reminderNotificationsEnabled := true
settings.SetReminderNotificationsEnabled(&reminderNotificationsEnabled) 
justificationRequiredOnApproval := true
settings.SetJustificationRequiredOnApproval(&justificationRequiredOnApproval) 
recommendationsEnabled := true
settings.SetRecommendationsEnabled(&recommendationsEnabled) 
instanceDurationInDays := int32(3)
settings.SetInstanceDurationInDays(&instanceDurationInDays) 
recurrence := graphmodels.NewPatternedRecurrence()
pattern := graphmodels.NewRecurrencePattern()
type := graphmodels.ABSOLUTEMONTHLY_RECURRENCEPATTERNTYPE 
pattern.SetType(&type) 
dayOfMonth := int32(5)
pattern.SetDayOfMonth(&dayOfMonth) 
interval := int32(3)
pattern.SetInterval(&interval) 
recurrence.SetPattern(pattern)
range := graphmodels.NewRecurrenceRange()
type := graphmodels.NOEND_RECURRENCERANGETYPE 
range.SetType(&type) 
startDate := "2020-05-04T00:00:00.000Z"
range.SetStartDate(&startDate) 
recurrence.SetRange(range)
settings.SetRecurrence(recurrence)
defaultDecisionEnabled := true
settings.SetDefaultDecisionEnabled(&defaultDecisionEnabled) 
defaultDecision := "Deny"
settings.SetDefaultDecision(&defaultDecision) 
autoApplyDecisionsEnabled := true
settings.SetAutoApplyDecisionsEnabled(&autoApplyDecisionsEnabled) 
requestBody.SetSettings(settings)

result, err := graphClient.IdentityGovernance().AccessReviews().Definitions().Post(requestBody)


```