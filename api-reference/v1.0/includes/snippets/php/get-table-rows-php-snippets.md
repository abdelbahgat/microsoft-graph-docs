---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestConfiguration = new RowsRequestBuilderGetRequestConfiguration();
$queryParameters = RowsRequestBuilderGetRequestConfiguration::createQueryParameters();
$queryParameters->top = 5;
$queryParameters->skip = 5;
$requestConfiguration->queryParameters = $queryParameters;


$result = $graphServiceClient->drives()->byDriveId('drive-id')->items()->byDriveItemId('driveItem-id')->workbook()->tables()->byWorkbookTableId('workbookTable-id')->rows()->get($requestConfiguration)->wait();

```