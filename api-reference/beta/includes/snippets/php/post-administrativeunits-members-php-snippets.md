---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new Group();
$requestBody->setOdataType('#microsoft.graph.group');
$requestBody->setDescription('Self help community for golf');
$requestBody->setDisplayName('Golf Assist');
$requestBody->setGroupTypes(['Unified', 	]);
$requestBody->setMailEnabled(true);
$requestBody->setMailNickname('golfassist');
$requestBody->setSecurityEnabled(false);

$result = $graphServiceClient->administrativeUnits()->byAdministrativeUnitId('administrativeUnit-id')->members()->post($requestBody)->wait();

```