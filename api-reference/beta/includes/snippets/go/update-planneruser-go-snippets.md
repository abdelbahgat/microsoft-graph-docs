---
description: "Automatically generated file. DO NOT MODIFY"
---

```go


import (
	  "context"
	  abstractions "github.com/microsoft/kiota-abstractions-go"
	  msgraphsdk "github.com/microsoftgraph/msgraph-beta-sdk-go"
	  graphmodels "github.com/microsoftgraph/msgraph-beta-sdk-go/models"
	  graphusers "github.com/microsoftgraph/msgraph-beta-sdk-go/users"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)


headers := abstractions.NewRequestHeaders()
headers.Add("Prefer", "return=representation")
headers.Add("If-Match", "W/\"JzEtVXNlckRldGFpbHMgQEBAQEBAQEBAQEBAQEBIWCc=\"")

configuration := &graphusers.ItemPlannerRequestBuilderPatchRequestConfiguration{
	Headers: headers,
}
requestBody := graphmodels.NewPlannerUser()
favoritePlanReferences := graphmodels.NewPlannerFavoritePlanReferenceCollection()
additionalData := map[string]interface{}{
jd8S5gOaFk2S8aWCIAJz42QAAxtD := graphmodels.NewPlannerFavoritePlanReference()
orderHint := " !"
jd8S5gOaFk2S8aWCIAJz42QAAxtD.SetOrderHint(&orderHint) 
planTitle := "Next Release Discussion"
jd8S5gOaFk2S8aWCIAJz42QAAxtD.SetPlanTitle(&planTitle) 
	favoritePlanReferences.SetJd8S5gOaFk2S8aWCIAJz42QAAxtD(jd8S5gOaFk2S8aWCIAJz42QAAxtD)
	"7oTB5aMIAE2rVo-1N-L7RmQAGX2q" := null
favoritePlanReferences.Set"7oTB5aMIAE2rVo-1N-L7RmQAGX2q"(&"7oTB5aMIAE2rVo-1N-L7RmQAGX2q") 
}
favoritePlanReferences.SetAdditionalData(additionalData)
requestBody.SetFavoritePlanReferences(favoritePlanReferences)
recentPlanReferences := graphmodels.NewPlannerRecentPlanReferenceCollection()
additionalData := map[string]interface{}{
jd8S5gOaFk2S8aWCIAJz42QAAxtD := graphmodels.NewPlannerRecentPlanReference()
lastAccessedDateTime , err := time.Parse(time.RFC3339, "2018-01-02T22:49:46.155Z")
jd8S5gOaFk2S8aWCIAJz42QAAxtD.SetLastAccessedDateTime(&lastAccessedDateTime) 
planTitle := "Next Release Discussion"
jd8S5gOaFk2S8aWCIAJz42QAAxtD.SetPlanTitle(&planTitle) 
	recentPlanReferences.SetJd8S5gOaFk2S8aWCIAJz42QAAxtD(jd8S5gOaFk2S8aWCIAJz42QAAxtD)
}
recentPlanReferences.SetAdditionalData(additionalData)
requestBody.SetRecentPlanReferences(recentPlanReferences)

planner, err := graphClient.Me().Planner().Patch(context.Background(), requestBody, configuration)


```