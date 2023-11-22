---
description: "Automatically generated file. DO NOT MODIFY"
---

```go


import (
	  "context"
	  msgraphsdk "github.com/microsoftgraph/msgraph-beta-sdk-go"
	  graphmodelsexternalconnectors "github.com/microsoftgraph/msgraph-beta-sdk-go/models/externalconnectors"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)


requestBody := graphmodelsexternalconnectors.NewSchema()
baseType := "microsoft.graph.externalItem"
requestBody.SetBaseType(&baseType) 


property := graphmodelsexternalconnectors.NewProperty()
name := "ticketTitle"
property.SetName(&name) 
type := graphmodels.STRING_PROPERTYTYPE 
property.SetType(&type) 
isSearchable := true
property.SetIsSearchable(&isSearchable) 
isRetrievable := true
property.SetIsRetrievable(&isRetrievable) 
labels := []graphmodelsexternalconnectors.Labelable {
	label := graphmodels.TITLE_LABEL 
	property.SetLabel(&label)
}
property.SetLabels(labels)
property1 := graphmodelsexternalconnectors.NewProperty()
name := "priority"
property1.SetName(&name) 
type := graphmodels.STRING_PROPERTYTYPE 
property1.SetType(&type) 
isQueryable := true
property1.SetIsQueryable(&isQueryable) 
isRetrievable := true
property1.SetIsRetrievable(&isRetrievable) 
isSearchable := false
property1.SetIsSearchable(&isSearchable) 
property2 := graphmodelsexternalconnectors.NewProperty()
name := "assignee"
property2.SetName(&name) 
type := graphmodels.STRING_PROPERTYTYPE 
property2.SetType(&type) 
isRetrievable := true
property2.SetIsRetrievable(&isRetrievable) 

properties := []graphmodelsexternalconnectors.Propertyable {
	property,
	property1,
	property2,
}
requestBody.SetProperties(properties)

schema, err := graphClient.External().Connections().ByExternalConnectionId("externalConnection-id").Schema().Patch(context.Background(), requestBody, nil)


```