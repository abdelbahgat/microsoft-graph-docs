---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW FOR THE KIOTA BASED SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($requestAdapter);

$requestBody = new BookingService();
$requestBody->set@odatatype('#microsoft.graph.bookingService');

$requestBody->setDefaultDuration('PT30M');



$graphServiceClient->solutions()->bookingBusinessesById('bookingBusiness-id')->servicesById('bookingService-id')->patch($requestBody);


```