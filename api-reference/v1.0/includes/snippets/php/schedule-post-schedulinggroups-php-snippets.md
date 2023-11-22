---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new SchedulingGroup();
$requestBody->setDisplayName('Cashiers');
$requestBody->setIsActive(true);
$requestBody->setUserIds(['c5d0c76b-80c4-481c-be50-923cd8d680a1', '2a4296b3-a28a-44ba-bc66-0274b9b95851', 	]);

$result = $graphServiceClient->teams()->byTeamId('team-id')->schedule()->schedulingGroups()->post($requestBody)->wait();

```