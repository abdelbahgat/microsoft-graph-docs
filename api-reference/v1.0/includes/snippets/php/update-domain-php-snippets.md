---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW FOR THE KIOTA BASED SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($requestAdapter);

$requestBody = new Domain();
$requestBody->setIsDefault(true);

$requestBody->setSupportedServices(['Email', 'OfficeCommunicationsOnline', ]);



$result = $graphServiceClient->domainsById('domain-id')->patch($requestBody);


```