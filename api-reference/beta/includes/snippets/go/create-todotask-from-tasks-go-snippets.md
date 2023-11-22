---
description: "Automatically generated file. DO NOT MODIFY"
---

```go


import (
	  "context"
	  msgraphsdk "github.com/microsoftgraph/msgraph-beta-sdk-go"
	  graphmodels "github.com/microsoftgraph/msgraph-beta-sdk-go/models"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)


requestBody := graphmodels.NewTodoTask()
title := "A new task"
requestBody.SetTitle(&title) 
categories := []string {
	"Important",
}
requestBody.SetCategories(categories)


linkedResource := graphmodels.NewLinkedResource()
webUrl := "http://microsoft.com"
linkedResource.SetWebUrl(&webUrl) 
applicationName := "Microsoft"
linkedResource.SetApplicationName(&applicationName) 
displayName := "Microsoft"
linkedResource.SetDisplayName(&displayName) 

linkedResources := []graphmodels.LinkedResourceable {
	linkedResource,
}
requestBody.SetLinkedResources(linkedResources)

tasks, err := graphClient.Me().Todo().Lists().ByTodoTaskListId("todoTaskList-id").Tasks().Post(context.Background(), requestBody, nil)


```