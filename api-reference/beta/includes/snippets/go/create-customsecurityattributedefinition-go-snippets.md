---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewCustomSecurityAttributeDefinition()
attributeSet := "Engineering"
requestBody.SetAttributeSet(&attributeSet) 
description := "Target completion date"
requestBody.SetDescription(&description) 
isCollection := false
requestBody.SetIsCollection(&isCollection) 
isSearchable := true
requestBody.SetIsSearchable(&isSearchable) 
name := "ProjectDate"
requestBody.SetName(&name) 
status := "Available"
requestBody.SetStatus(&status) 
type := "String"
requestBody.SetType(&type) 
usePreDefinedValuesOnly := false
requestBody.SetUsePreDefinedValuesOnly(&usePreDefinedValuesOnly) 

result, err := graphClient.Directory().CustomSecurityAttributeDefinitions().Post(requestBody)


```