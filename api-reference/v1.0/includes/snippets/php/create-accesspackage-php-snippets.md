---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new AccessPackage();
$requestBody->setDisplayName('sales reps');
$requestBody->setDescription('outside sales representatives');
$requestBody->setIsHidden(false);
$catalog = new AccessPackageCatalog();
$catalog->setId('66584aae-98bb-48cc-9458-7bee5d2a6577');
$requestBody->setCatalog($catalog);

$result = $graphServiceClient->identityGovernance()->entitlementManagement()->accessPackages()->post($requestBody)->wait();

```