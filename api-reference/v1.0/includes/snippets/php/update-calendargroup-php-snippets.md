---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW FOR THE KIOTA BASED SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($requestAdapter);

$requestBody = new CalendarGroup();
$requestBody->setName('name-value');



$result = $graphServiceClient->me()->calendarGroupsById('calendarGroup-id')->patch($requestBody);


```