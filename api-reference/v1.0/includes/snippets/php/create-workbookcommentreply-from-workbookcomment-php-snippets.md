---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW FOR THE KIOTA BASED SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($requestAdapter);

$requestBody = new WorkbookCommentReply();
$requestBody->setContent('This is my reply to the comment.');

$requestBody->setContentType('plain');



$result = $graphServiceClient->drivesById('drive-id')->itemsById('driveItem-id')->workbook()->commentsById('workbookComment-id')->replies()->post($requestBody);


```