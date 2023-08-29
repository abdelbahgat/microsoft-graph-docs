---
description: "Automatically generated file. DO NOT MODIFY"
---

```java

GraphServiceClient graphClient = GraphServiceClient.builder().authenticationProvider( authProvider ).buildClient();

LinkedList<Recipient> toRecipientsList = new LinkedList<Recipient>();
Recipient toRecipients = new Recipient();
EmailAddress emailAddress = new EmailAddress();
emailAddress.address = "danas@contoso.onmicrosoft.com";
emailAddress.name = "Dana Swope";
toRecipients.emailAddress = emailAddress;

toRecipientsList.add(toRecipients);

String comment = "Dana, hope you can make this meeting.";

graphClient.me().events("{id}")
	.forward(EventForwardParameterSet
		.newBuilder()
		.withToRecipients(toRecipientsList)
		.withComment(comment)
		.build())
	.buildRequest()
	.post();

```