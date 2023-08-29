---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW FOR THE KIOTA BASED SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($requestAdapter);

$requestBody = new Group();
$requestBody->setDescription('Group assignable to a role');

$requestBody->setDisplayName('Role assignable group');

$requestBody->setGroupTypes(['Unified', ]);

$requestBody->setIsAssignableToRole(true);

$requestBody->setMailEnabled(true);

$requestBody->setSecurityEnabled(true);

$requestBody->setMailNickname('contosohelpdeskadministrators');

$additionalData = [
'owners@odata.bind' => ['https://graph.microsoft.com/beta/users/99e44b05-c10b-4e95-a523-e2732bbaba1e', ],
'members@odata.bind' => ['https://graph.microsoft.com/beta/users/6ea91a8d-e32e-41a1-b7bd-d2d185eed0e0', 'https://graph.microsoft.com/beta/users/4562bcc8-c436-4f95-b7c0-4f8ce89dca5e', ],
];
$requestBody->setAdditionalData($additionalData);




$requestResult = $graphServiceClient->groups()->post($requestBody);


```