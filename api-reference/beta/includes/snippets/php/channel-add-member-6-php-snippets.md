---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW FOR THE KIOTA BASED SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($requestAdapter);

$requestBody = new ConversationMember();
$requestBody->set@odatatype('#microsoft.graph.aadUserConversationMember');

$requestBody->setRoles(]);

$additionalData = [
'user@odata.bind' => 'https://graph.microsoft.com/beta/users(\'jacob@contoso.com\')', 
];
$requestBody->setAdditionalData($additionalData);




$requestResult = $graphServiceClient->teamsById('team-id')->channelsById('channel-id')->members()->post($requestBody);


```