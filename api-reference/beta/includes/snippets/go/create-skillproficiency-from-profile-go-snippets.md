---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewSkillProficiency()
categories := []String {
	"Professional",

}
requestBody.SetCategories(categories)
allowedAudiences := graphmodels.ORGANIZATION_ALLOWEDAUDIENCES 
requestBody.SetAllowedAudiences(&allowedAudiences) 
displayName := "API Design"
requestBody.SetDisplayName(&displayName) 
proficiency := graphmodels.GENERALPROFESSIONAL_SKILLPROFICIENCYLEVEL 
requestBody.SetProficiency(&proficiency) 
collaborationTags := []String {
	"ableToMentor",

}
requestBody.SetCollaborationTags(collaborationTags)

result, err := graphClient.Me().Profile().Skills().Post(requestBody)


```