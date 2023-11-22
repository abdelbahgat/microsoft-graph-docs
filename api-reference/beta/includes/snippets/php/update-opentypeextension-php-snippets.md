---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new Extension();
$requestBody->setOdataType('#microsoft.outlookServices.openTypeExtension');
$additionalData = [
	'extensionName' => 'Com.Contoso.Estimate',
	'companyName' => 'Contoso',
	'expirationDate' => '2016-07-30T11:00:00.000Z',
	'DealValue' => 1010100,
	'topPicks' => [
'Employees only', 'Add spouse or guest', 'Add family', ],
];
$requestBody->setAdditionalData($additionalData);

$result = $graphServiceClient->groups()->byGroupId('group-id')->threads()->byConversationThreadId('conversationThread-id')->posts()->byPostId('post-id')->extensions()->byExtensionId('extension-id')->patch($requestBody)->wait();

```