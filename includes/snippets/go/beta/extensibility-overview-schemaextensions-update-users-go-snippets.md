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


requestBody := graphmodels.NewUser()
additionalData := map[string]interface{}{
extkmpdyld2_graphLearnCourses := graphmodels.New()
courseType := "Instructor-led"
extkmpdyld2_graphLearnCourses.SetCourseType(&courseType) 
	courseId := null
extkmpdyld2_graphLearnCourses.SetCourseId(&courseId) 
	requestBody.SetExtkmpdyld2_graphLearnCourses(extkmpdyld2_graphLearnCourses)
}
requestBody.SetAdditionalData(additionalData)

users, err := graphClient.Users().ByUserId("user-id").Patch(context.Background(), requestBody, nil)


```