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


requestBody := graphmodels.NewListItem()
fields := graphmodels.NewFieldValueSet()
additionalData := map[string]interface{}{
	"title" : "Widget", 
	"color" : "Purple", 
	"weight" : int32(32) , 
}
fields.SetAdditionalData(additionalData)
requestBody.SetFields(fields)

items, err := graphClient.Sites().BySiteId("site-id").Lists().ByListId("list-id").Items().Post(context.Background(), requestBody, nil)


```