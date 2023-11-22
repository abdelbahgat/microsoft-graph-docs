---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new RefreshSessionPostRequestBody();
$requestConfiguration = new RefreshSessionRequestBuilderPostRequestConfiguration();
$headers = [
		'workbook-session-id' => '{session-id}',
	];
$requestConfiguration->headers = $headers;


$graphServiceClient->drives()->byDriveId('drive-id')->items()->byDriveItemId('driveItem-id')->workbook()->refreshSession()->post($requestBody, $requestConfiguration)->wait();

```