---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);


$graphServiceClient->bookingBusinesses()->byBookingBusinessId('bookingBusiness-id')->services()->byBookingServiceId('bookingService-id')->delete()->wait();

```