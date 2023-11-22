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


requestBody := graphmodels.NewPersonInterest()
categories := []string {
	"Sports",
}
requestBody.SetCategories(categories)
description := "World's greatest football club"
requestBody.SetDescription(&description) 
displayName := "Chelsea FC"
requestBody.SetDisplayName(&displayName) 
webUrl := "https://www.chelseafc.com"
requestBody.SetWebUrl(&webUrl) 

interests, err := graphClient.Me().Profile().Interests().Post(context.Background(), requestBody, nil)


```