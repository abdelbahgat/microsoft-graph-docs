---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new AddFormulaLocalPostRequestBody();
$requestBody->setName('test7');
$requestBody->setFormula('=SUM(Sheet2!$A$1+Sheet2!$A$2)');
$requestBody->setComment('Comment for the named item');

$result = $graphServiceClient->drives()->byDriveId('drive-id')->items()->byDriveItemId('driveItem-id')->workbook()->names()->addFormulaLocal()->post($requestBody)->wait();

```