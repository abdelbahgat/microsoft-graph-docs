---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new AdministrativeUnit();
$requestBody->setDisplayName('Executive Division');
$requestBody->setDescription('Executive division administration');
$requestBody->setIsMemberManagementRestricted(true);

$result = $graphServiceClient->administrativeUnits()->post($requestBody)->wait();

```