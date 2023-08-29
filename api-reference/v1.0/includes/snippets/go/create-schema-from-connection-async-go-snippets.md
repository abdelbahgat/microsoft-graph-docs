---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewSchemaPostRequestBody()
additionalData := map[string]interface{}{
	"baseType" : "microsoft.graph.externalItem", 


 := graphmodels.New()
name := "ticketTitle"
.SetName(&name) 
type := "String"
.SetType(&type) 
isSearchable := "true"
.SetIsSearchable(&isSearchable) 
isRetrievable := "true"
.SetIsRetrievable(&isRetrievable) 
labels := []String {
	"title",

}
.SetLabels(labels)
 := graphmodels.New()
name := "priority"
.SetName(&name) 
type := "String"
.SetType(&type) 
isQueryable := "true"
.SetIsQueryable(&isQueryable) 
isRetrievable := "true"
.SetIsRetrievable(&isRetrievable) 
isSearchable := "false"
.SetIsSearchable(&isSearchable) 
 := graphmodels.New()
name := "assignee"
.SetName(&name) 
type := "String"
.SetType(&type) 
isRetrievable := "true"
.SetIsRetrievable(&isRetrievable) 

	properties := []graphmodels.Objectable {
		,
		,
		,

	}
}
requestBody.SetAdditionalData(additionalData)

graphClient.External().ConnectionsById("externalConnection-id").Schema().Post(requestBody)


```