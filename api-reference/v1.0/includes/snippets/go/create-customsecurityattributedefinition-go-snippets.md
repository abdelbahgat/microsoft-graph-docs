---
description: "Automatically generated file. DO NOT MODIFY"
---

```go


import (
	  "context"
	  msgraphsdk "github.com/microsoftgraph/msgraph-sdk-go"
	  graphmodels "github.com/microsoftgraph/msgraph-sdk-go/models"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)


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

customSecurityAttributeDefinitions, err := graphClient.Directory().CustomSecurityAttributeDefinitions().Post(context.Background(), requestBody, nil)


```