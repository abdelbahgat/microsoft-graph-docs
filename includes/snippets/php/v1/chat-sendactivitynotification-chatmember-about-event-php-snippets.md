---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new SendActivityNotificationPostRequestBody();
$topic = new TeamworkActivityTopic();
$topic->setSource(new TeamworkActivityTopicSource('text'));
$topic->setValue('Weekly Virtual Social');
$topic->setWebUrl('https://teams.microsoft.com/l/message/19:448cfd2ac2a7490a9084a9ed14cttr78c@thread.skype/1605223780000?tenantId=c8b1bf45-3834-4ecf-971a-b4c755ee677d&groupId=d4c2a937-f097-435a-bc91-5c1683ca7245&parentMessageId=1605223771864&teamName=Approvals&channelName=Azure%20DevOps&createdTime=1605223780000');
$requestBody->setTopic($topic);
$previewText = new ItemBody();
$previewText->setContent('It will be fun!');
$requestBody->setPreviewText($previewText);
$requestBody->setActivityType('eventCreated');
$recipient = new ChatMembersNotificationRecipient();
$recipient->setOdataType('microsoft.graph.chatMembersNotificationRecipient');
$recipient->setChatId('19:d65713bc498c4a428c71ef9353e6ce20@thread.v2');
$requestBody->setRecipient($recipient);

$graphServiceClient->chats()->byChatId('chat-id')->sendActivityNotification()->post($requestBody)->wait();

```