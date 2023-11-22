---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new AccessPackageResourceRequest();
$requestBody->setRequestType(new AccessPackageRequestType('adminAdd'));
$resource = new AccessPackageResource();
$resource->setOriginId('https://microsoft.sharepoint.com/sites/Example');
$resource->setOriginSystem('SharePointOnline');
$requestBody->setResource($resource);
$catalog = new AccessPackageCatalog();
$catalog->setId('beedadfe-01d5-4025-910b-84abb9369997');
$requestBody->setCatalog($catalog);

$result = $graphServiceClient->identityGovernance()->entitlementManagement()->resourceRequests()->post($requestBody)->wait();

```