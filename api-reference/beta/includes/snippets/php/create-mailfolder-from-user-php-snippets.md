---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW FOR THE KIOTA BASED SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($requestAdapter);

$requestBody = new MailFolder();
$requestBody->setDisplayName('Clutter');

$requestBody->setIsHidden(true);



$requestResult = $graphServiceClient->me()->mailFolders()->post($requestBody);


```