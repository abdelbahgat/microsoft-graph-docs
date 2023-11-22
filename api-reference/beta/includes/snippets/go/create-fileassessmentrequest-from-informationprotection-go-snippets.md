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


requestBody := graphmodels.NewThreatAssessmentRequest()
expectedAssessment := graphmodels.BLOCK_THREATEXPECTEDASSESSMENT 
requestBody.SetExpectedAssessment(&expectedAssessment) 
category := graphmodels.MALWARE_THREATCATEGORY 
requestBody.SetCategory(&category) 
fileName := "test.txt"
requestBody.SetFileName(&fileName) 
contentData := "VGhpcyBpcyBhIHRlc3QgZmlsZQ=="
requestBody.SetContentData(&contentData) 

threatAssessmentRequests, err := graphClient.InformationProtection().ThreatAssessmentRequests().Post(context.Background(), requestBody, nil)


```