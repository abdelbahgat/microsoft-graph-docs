---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new CancelPostRequestBody();
$requestBody->setCancellationMessage('Your appointment has been successfully cancelled. Please call us again.');

$graphServiceClient->solutions()->bookingBusinesses()->byBookingBusinessId('bookingBusiness-id')->appointments()->byBookingAppointmentId('bookingAppointment-id')->cancel()->post($requestBody)->wait();

```