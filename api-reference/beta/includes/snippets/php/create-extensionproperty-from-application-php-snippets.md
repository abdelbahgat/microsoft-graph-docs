---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW FOR THE KIOTA BASED SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($requestAdapter);

$requestBody = new ExtensionProperty();
$requestBody->setName('jobGroup');

$requestBody->setDataType('String');

$requestBody->setTargetObjects(['User', ]);



$requestResult = $graphServiceClient->applicationsById('application-id')->extensionProperties()->post($requestBody);


```