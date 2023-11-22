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


requestBody := graphmodels.NewAuthoredNote()
content := graphmodels.NewItemBody()
content := "Please take a look at the files tagged with follow up"
content.SetContent(&content) 
contentType := graphmodels.TEXT_BODYTYPE 
content.SetContentType(&contentType) 
requestBody.SetContent(content)

notes, err := graphClient.Privacy().SubjectRightsRequests().BySubjectRightsRequestId("subjectRightsRequest-id").Notes().Post(context.Background(), requestBody, nil)


```