---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

educationClassId := "educationClass-id"
educationUserId := "educationUser-id"
graphClient.Education().ClassesById(&educationClassId).MembersById(&educationUserId).Delete()


```