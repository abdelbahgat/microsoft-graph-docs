---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new AccessPackageResourceRequest();
$requestBody->setRequestType(new AccessPackageRequestType('adminRemove'));
$resource = new AccessPackageResource();
$resource->setId('1d0bb962-5bb0-4b16-a488-fda7a788b9ec');
$requestBody->setResource($resource);
$catalog = new AccessPackageCatalog();
$catalog->setId('beedadfe-01d5-4025-910b-84abb9369997');
$requestBody->setCatalog($catalog);

$result = $graphServiceClient->identityGovernance()->entitlementManagement()->resourceRequests()->post($requestBody)->wait();

```