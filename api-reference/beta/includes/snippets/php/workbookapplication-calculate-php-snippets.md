---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW FOR THE KIOTA BASED SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($requestAdapter);

$requestBody = new CalculatePostRequestBody();
$requestBody->setCalculationType('calculationType-value');



$graphServiceClient->drivesById('drive-id')->itemsById('driveItem-id')->workbook()->application()->calculate()->post($requestBody);


```