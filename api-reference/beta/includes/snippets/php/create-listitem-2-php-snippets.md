---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW FOR THE KIOTA BASED SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($requestAdapter);

$requestBody = new FieldValueSet();
$additionalData = [
'Color' => 'Fuchsia', 
'Quantity' => 934,
];
$requestBody->setAdditionalData($additionalData);




$graphServiceClient->sitesById('site-id')->listsById('list-id')->itemsById('listItem-id')->fields()->patch($requestBody);


```