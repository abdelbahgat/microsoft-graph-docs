---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)


result, err := graphClient.ServicePrincipalsById("servicePrincipal-id").Synchronization().JobsById("synchronizationJob-id").Schema().DirectoriesById("directoryDefinition-id").Discover(servicePrincipal-id, synchronizationJob-id, directoryDefinition-id).Post()


```