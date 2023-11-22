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


requestBody := graphmodels.NewEducationSchool()
displayName := "Fabrikam Arts High School"
requestBody.SetDisplayName(&displayName) 
description := "Magnate school for the arts. Los Angeles School District"
requestBody.SetDescription(&description) 

schools, err := graphClient.Education().Schools().ByEducationSchoolId("educationSchool-id").Patch(context.Background(), requestBody, nil)


```