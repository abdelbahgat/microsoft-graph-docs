---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW FOR THE KIOTA BASED SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($requestAdapter);

$requestBody = new ExternalGroup();
$requestBody->setDisplayName('Contoso Marketing');

$requestBody->setDescription('The product marketing team');



$result = $graphServiceClient->external()->connectionsById('externalConnection-id')->groupsById('externalGroup-id')->patch($requestBody);


```