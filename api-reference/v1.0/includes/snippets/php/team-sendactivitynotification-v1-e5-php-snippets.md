---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new SendActivityNotificationPostRequestBody();
$topic = new TeamworkActivityTopic();
$topic->setSource(new TeamworkActivityTopicSource('entityUrl'));
$topic->setValue('https://graph.microsoft.com/v1.0/teams/e8bece96-d393-4b9b-b8da-69cedef1a7e7');
$requestBody->setTopic($topic);
$requestBody->setActivityType('pendingFinanceApprovalRequests');
$previewText = new ItemBody();
$previewText->setContent('Internal spending team has a pending finance approval requests');
$requestBody->setPreviewText($previewText);
$recipient = new TeamMembersNotificationRecipient();
$recipient->setOdataType('microsoft.graph.teamMembersNotificationRecipient');
$recipient->setTeamId('e8bece96-d393-4b9b-b8da-69cedef1a7e7');
$requestBody->setRecipient($recipient);
$templateParametersKeyValuePair1 = new KeyValuePair();
$templateParametersKeyValuePair1->setName('pendingRequestCount');
$templateParametersKeyValuePair1->setValue('5');
$templateParametersArray []= $templateParametersKeyValuePair1;
$requestBody->setTemplateParameters($templateParametersArray);


$graphServiceClient->teams()->byTeamId('team-id')->sendActivityNotification()->post($requestBody)->wait();

```