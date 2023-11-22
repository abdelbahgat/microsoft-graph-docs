---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestConfiguration = new CalendarViewRequestBuilderGetRequestConfiguration();
$queryParameters = CalendarViewRequestBuilderGetRequestConfiguration::createQueryParameters();
$queryParameters->start = "2018-04-30T00:00:00Z";
$queryParameters->end = "2018-05-10T00:00:00Z";
$requestConfiguration->queryParameters = $queryParameters;


$result = $graphServiceClient->bookingBusinesses()->byBookingBusinessId('bookingBusiness-id')->calendarView()->get($requestConfiguration)->wait();

```