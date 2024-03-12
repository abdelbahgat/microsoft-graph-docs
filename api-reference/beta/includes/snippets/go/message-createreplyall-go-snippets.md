---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
import (
	  "context"
	  msgraphsdk "github.com/microsoftgraph/msgraph-beta-sdk-go"
	  graphmodels "github.com/microsoftgraph/msgraph-beta-sdk-go/Me/Messages/Item/CreateReplyAll"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)


requestBody := graphmodels.NewCreateReplyAllPostRequestBody()
message := graphmodels.NewMessage()


attachment := graphmodels.NewAttachment()
name := "guidelines.txt"
attachment.SetName(&name) 
additionalData := map[string]interface{}{
	"contentBytes" : "bWFjIGFuZCBjaGVlc2UgdG9kYXk=", 
}
attachment.SetAdditionalData(additionalData)

attachments := []graphmodels.Attachmentable {
	attachment,

}
message.SetAttachments(attachments)
requestBody.SetMessage(message)
comment := "if the project gets approved, please take a look at the attached guidelines before you decide on the name."
requestBody.SetComment(&comment) 

result, err := graphClient.Me().Messages().ByMessageId("message-id").CreateReplyAll().Post(context.Background(), requestBody, nil)


```