---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new GroupSetting();
$requestBody->setTemplateId('08d542b9-071f-4e16-94b0-74abb372e3d9');
$valuesSettingValue1 = new SettingValue();
$valuesSettingValue1->setName('AllowToAddGuests');
$valuesSettingValue1->setValue('false');
$valuesArray []= $valuesSettingValue1;
$requestBody->setValues($valuesArray);


$result = $graphServiceClient->groups()->byGroupId('group-id')->settings()->post($requestBody)->wait();

```