---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new AccessPackageCatalog();
$requestBody->setDisplayName('sales');
$requestBody->setDescription('for employees working with sales and outside sales partners');
$requestBody->setState(new AccessPackageCatalogState('published'));
$requestBody->setIsExternallyVisible(true);

$result = $graphServiceClient->identityGovernance()->entitlementManagement()->catalogs()->post($requestBody)->wait();

```