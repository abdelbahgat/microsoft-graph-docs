---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new WorkbookChartFont();
$requestBody->setBold(true);
$requestBody->setColor('color-value');
$requestBody->setItalic(true);
$requestBody->setName('name-value');
$requestBody->setSize(99);
$requestBody->setUnderline('underline-value');

$result = $graphServiceClient->drives()->byDriveId('drive-id')->items()->byDriveItemId('driveItem-id')->workbook()->worksheets()->byWorkbookWorksheetId('workbookWorksheet-id')->charts()->byWorkbookChartId('workbookChart-id')->axes()->valueAxis()->format()->font()->patch($requestBody)->wait();

```