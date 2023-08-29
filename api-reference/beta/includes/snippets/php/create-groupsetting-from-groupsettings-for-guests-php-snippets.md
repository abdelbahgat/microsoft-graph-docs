---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW FOR THE KIOTA BASED SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($requestAdapter);

$requestBody = new DirectorySetting();
$requestBody->setTemplateId('08d542b9-071f-4e16-94b0-74abb372e3d9');

$valuesSettingValue1 = new SettingValue();
$additionalData = [
'name' => 'AllowToAddGuests', 
'value' => 'false', 
];
$valuesSettingValue1->setAdditionalData($additionalData);



$valuesArray []= $valuesSettingValue1;
$requestBody->setValues($valuesArray);




$requestResult = $graphServiceClient->groupsById('group-id')->settings()->post($requestBody);


```