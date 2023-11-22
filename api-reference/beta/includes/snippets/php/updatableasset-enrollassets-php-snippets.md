---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new EnrollAssetsPostRequestBody();
$requestBody->setUpdateCategory(new UpdateCategory('string'));
$assetsUpdatableAsset1 = new AzureADDevice();
$assetsUpdatableAsset1->setOdataType('#microsoft.graph.windowsUpdates.azureADDevice');
$assetsUpdatableAsset1->setId('String (identifier)');
$assetsArray []= $assetsUpdatableAsset1;
$requestBody->setAssets($assetsArray);


$graphServiceClient->admin()->windows()->updates()->updatableAssets()->microsoftGraphWindowsUpdatesEnrollAssets()->post($requestBody)->wait();

```