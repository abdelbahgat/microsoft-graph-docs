---
description: "Automatically generated file. DO NOT MODIFY"
---

```java

GraphServiceClient graphClient = GraphServiceClient.builder().authenticationProvider( authProvider ).buildClient();

TeamworkActivityTopic topic = new TeamworkActivityTopic();
topic.source = TeamworkActivityTopicSource.ENTITY_URL;
topic.value = "https://graph.microsoft.com/beta/teams/e8bece96-d393-4b9b-b8da-69cedef1a7e7";

String activityType = "pendingFinanceApprovalRequests";

ItemBody previewText = new ItemBody();
previewText.content = "Internal spending team has a pending finance approval requests";

ChannelMembersNotificationRecipient recipient = new ChannelMembersNotificationRecipient();
recipient.teamId = "e8bece96-d393-4b9b-b8da-69cedef1a7e7";
recipient.channelId = "19:3d61a2309f094f4a9310b20f1db37520@thread.tacv2";

LinkedList<KeyValuePair> templateParametersList = new LinkedList<KeyValuePair>();
KeyValuePair templateParameters = new KeyValuePair();
templateParameters.name = "pendingRequestCount";
templateParameters.value = "5";

templateParametersList.add(templateParameters);

graphClient.teams("e8bece96-d393-4b9b-b8da-69cedef1a7e7")
	.sendActivityNotification(TeamSendActivityNotificationParameterSet
		.newBuilder()
		.withTopic(topic)
		.withActivityType(activityType)
		.withChainId(null)
		.withPreviewText(previewText)
		.withTemplateParameters(templateParametersList)
		.withRecipient(recipient)
		.build())
	.buildRequest()
	.post();

```