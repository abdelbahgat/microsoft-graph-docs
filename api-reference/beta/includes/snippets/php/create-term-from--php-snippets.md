---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW FOR THE KIOTA BASED SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($requestAdapter);

$requestBody = new Term();
$labelsLocalizedLabel1 = new LocalizedLabel();
$labelsLocalizedLabel1->setLanguageTag('en-US');

$labelsLocalizedLabel1->setName('Car');

$labelsLocalizedLabel1->setIsDefault(true);


$labelsArray []= $labelsLocalizedLabel1;
$requestBody->setLabels($labelsArray);




$requestResult = $graphServiceClient->termStore()->setsById('set-id')->children()->post($requestBody);


```