---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW FOR THE KIOTA BASED SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($requestAdapter);

$requestBody = new Team();
$additionalData = [
'template@odata.bind' => 'https://graph.microsoft.com/beta/teamsTemplates(\'standard\')', 
'group@odata.bind' => 'https://graph.microsoft.com/beta/groups(\'71392b2f-1765-406e-86af-5907d9bdb2ab\')', 
];
$requestBody->setAdditionalData($additionalData);




$requestResult = $graphServiceClient->teams()->post($requestBody);


```