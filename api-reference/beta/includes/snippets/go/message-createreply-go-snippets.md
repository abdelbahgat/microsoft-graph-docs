---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewCreateReplyPostRequestBody()
message := graphmodels.Newmessage()


recipient := graphmodels.NewRecipient()
emailAddress := graphmodels.NewEmailAddress()
address := "samanthab@contoso.onmicrosoft.com"
emailAddress.SetAddress(&address) 
name := "Samantha Booth"
emailAddress.SetName(&name) 
recipient.SetEmailAddress(emailAddress)
recipient1 := graphmodels.NewRecipient()
emailAddress := graphmodels.NewEmailAddress()
address := "randiw@contoso.onmicrosoft.com"
emailAddress.SetAddress(&address) 
name := "Randi Welch"
emailAddress.SetName(&name) 
recipient1.SetEmailAddress(emailAddress)

toRecipients := []graphmodels.Recipientable {
	recipient,
	recipient1,

}
message.SetToRecipients(toRecipients)
requestBody.SetMessage(message)
comment := "Samantha, Randi, would you name the group if the project is approved, please?"
requestBody.SetComment(&comment) 

result, err := graphClient.Me().MessagesById("message-id").CreateReply(message-id).Post(requestBody)


```