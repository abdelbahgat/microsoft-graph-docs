---
description: "Automatically generated file. DO NOT MODIFY"
---

```go


import (
	  "context"
	  msgraphsdk "github.com/microsoftgraph/msgraph-beta-sdk-go"
	  graphmodelssearch "github.com/microsoftgraph/msgraph-beta-sdk-go/models/search"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)


requestBody := graphmodelssearch.NewBookmark()
displayName := "Contoso Install Site"
requestBody.SetDisplayName(&displayName) 
webUrl := "http://www.contoso.com/"
requestBody.SetWebUrl(&webUrl) 
description := "Try or buy Contoso for Home or Business and view product information"
requestBody.SetDescription(&description) 
keywords := graphmodelssearch.NewAnswerKeyword()
keywords := []string {
	"Contoso",
	"install",
}
keywords.SetKeywords(keywords)
reservedKeywords := []string {
	"Contoso",
}
keywords.SetReservedKeywords(reservedKeywords)
matchSimilarKeywords := true
keywords.SetMatchSimilarKeywords(&matchSimilarKeywords) 
requestBody.SetKeywords(keywords)
state := graphmodels.PUBLISHED_ANSWERSTATE 
requestBody.SetState(&state) 

bookmarks, err := graphClient.Search().Bookmarks().Post(context.Background(), requestBody, nil)


```