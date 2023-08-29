---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewSchemaPostRequestBody()
additionalData := map[string]interface{}{


 := graphmodels.New()
name := "Azure Active Directory"
.SetName(&name) 


 := graphmodels.New()
name := "User"
.SetName(&name) 


 := graphmodels.New()
name := "userPrincipalName"
.SetName(&name) 
type := "string"
.SetType(&type) 

attributes := []graphmodels.Objectable {
	,

}
.SetAttributes(attributes)

objects := []graphmodels.Objectable {
	,

}
.SetObjects(objects)
 := graphmodels.New()
name := "Salesforce"
.SetName(&name) 

	directories := []graphmodels.Objectable {
		,
		,

	}


 := graphmodels.New()
name := "USER_TO_USER"
.SetName(&name) 
sourceDirectoryName := "Azure Active Directory"
.SetSourceDirectoryName(&sourceDirectoryName) 
targetDirectoryName := "Salesforce"
.SetTargetDirectoryName(&targetDirectoryName) 


 := graphmodels.New()
sourceObjectName := "User"
.SetSourceObjectName(&sourceObjectName) 
targetObjectName := "User"
.SetTargetObjectName(&targetObjectName) 


 := graphmodels.New()
source := graphmodels.New()
.SetSource(source)
targetAttributeName := "userName"
.SetTargetAttributeName(&targetAttributeName) 

attributeMappings := []graphmodels.Objectable {
	,

}
.SetAttributeMappings(attributeMappings)

objectMappings := []graphmodels.Objectable {
	,

}
.SetObjectMappings(objectMappings)

	synchronizationRules := []graphmodels.Objectable {
		,

	}
}
requestBody.SetAdditionalData(additionalData)

graphClient.ServicePrincipalsById("servicePrincipal-id").Synchronization().JobsById("synchronizationJob-id").Schema().Put(requestBody)


```