---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewStringKeyStringValuePairPostRequestBody()


synchronizationJobApplicationParameters := graphmodels.NewSynchronizationJobApplicationParameters()
ruleId := "33f7c90d-bf71-41b1-bda6-aaf0ddbee5d8#V2"
synchronizationJobApplicationParameters.SetRuleId(&ruleId) 


synchronizationJobSubject := graphmodels.NewSynchronizationJobSubject()
objectId := "8213fd99-d6b6-417b-8e13-af6334856215"
synchronizationJobSubject.SetObjectId(&objectId) 
objectTypeName := "Group"
synchronizationJobSubject.SetObjectTypeName(&objectTypeName) 
links := graphmodels.NewSynchronizationLinkedObjects()


synchronizationJobSubject := graphmodels.NewSynchronizationJobSubject()
objectId := "cbc86211-6ada-4803-b73f-8039cf56d8a2"
synchronizationJobSubject.SetObjectId(&objectId) 
objectTypeName := "User"
synchronizationJobSubject.SetObjectTypeName(&objectTypeName) 
synchronizationJobSubject1 := graphmodels.NewSynchronizationJobSubject()
objectId := "2bc86211-6ada-4803-b73f-8039cf56d8a2"
synchronizationJobSubject1.SetObjectId(&objectId) 
objectTypeName := "User"
synchronizationJobSubject1.SetObjectTypeName(&objectTypeName) 

members := []graphmodels.SynchronizationJobSubjectable {
	synchronizationJobSubject,
	synchronizationJobSubject1,

}
links.SetMembers(members)
synchronizationJobSubject.SetLinks(links)

subjects := []graphmodels.SynchronizationJobSubjectable {
	synchronizationJobSubject,

}
synchronizationJobApplicationParameters.SetSubjects(subjects)

parameters := []graphmodels.SynchronizationJobApplicationParametersable {
	synchronizationJobApplicationParameters,

}
requestBody.SetParameters(parameters)

result, err := graphClient.ServicePrincipalsById("servicePrincipal-id").Synchronization().JobsById("synchronizationJob-id").ProvisionOnDemand(servicePrincipal-id, synchronizationJob-id).Post(requestBody)


```