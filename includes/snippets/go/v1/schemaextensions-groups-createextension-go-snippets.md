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


requestBody := graphmodels.NewSchemaExtension()
id := "graphlearn_courses"
requestBody.SetId(&id) 
description := "Graph Learn training courses extensions"
requestBody.SetDescription(&description) 
targetTypes := []string {
	"Group",
}
requestBody.SetTargetTypes(targetTypes)


extensionSchemaProperty := graphmodels.NewExtensionSchemaProperty()
name := "courseId"
extensionSchemaProperty.SetName(&name) 
type := "Integer"
extensionSchemaProperty.SetType(&type) 
extensionSchemaProperty1 := graphmodels.NewExtensionSchemaProperty()
name := "courseName"
extensionSchemaProperty1.SetName(&name) 
type := "String"
extensionSchemaProperty1.SetType(&type) 
extensionSchemaProperty2 := graphmodels.NewExtensionSchemaProperty()
name := "courseType"
extensionSchemaProperty2.SetName(&name) 
type := "String"
extensionSchemaProperty2.SetType(&type) 

properties := []graphmodels.ExtensionSchemaPropertyable {
	extensionSchemaProperty,
	extensionSchemaProperty1,
	extensionSchemaProperty2,
}
requestBody.SetProperties(properties)

schemaExtensions, err := graphClient.SchemaExtensions().Post(context.Background(), requestBody, nil)


```