---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new AccessPackage();
$requestBody->setDisplayName('Access Package New Name');

$result = $graphServiceClient->identityGovernance()->entitlementManagement()->accessPackages()->byAccessPackageId('accessPackage-id')->patch($requestBody)->wait();

```