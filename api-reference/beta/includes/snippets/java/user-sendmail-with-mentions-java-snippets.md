---
description: "Automatically generated file. DO NOT MODIFY"
---

```java

GraphServiceClient graphClient = GraphServiceClient.builder().authenticationProvider( authProvider ).buildClient();

Message message = new Message();
message.subject = "Project kickoff";
LinkedList<Recipient> toRecipientsList = new LinkedList<Recipient>();
Recipient toRecipients = new Recipient();
EmailAddress emailAddress = new EmailAddress();
emailAddress.name = "Samantha Booth";
emailAddress.address = "samanthab@contoso.onmicrosoft.com";
toRecipients.emailAddress = emailAddress;
toRecipientsList.add(toRecipients);
message.toRecipients = toRecipientsList;
LinkedList<Mention> mentionsList = new LinkedList<Mention>();
Mention mentions = new Mention();
EmailAddress mentioned = new EmailAddress();
mentioned.name = "Dana Swope";
mentioned.address = "danas@contoso.onmicrosoft.com";
mentions.mentioned = mentioned;
mentionsList.add(mentions);
MentionCollectionResponse mentionCollectionResponse = new MentionCollectionResponse();
mentionCollectionResponse.value = mentionsList;
MentionCollectionPage mentionCollectionPage = new MentionCollectionPage(mentionCollectionResponse, null);
message.mentions = mentionCollectionPage;

graphClient.me()
	.sendMail(UserSendMailParameterSet
		.newBuilder()
		.withMessage(message)
		.withSaveToSentItems(null)
		.build())
	.buildRequest()
	.post();

```