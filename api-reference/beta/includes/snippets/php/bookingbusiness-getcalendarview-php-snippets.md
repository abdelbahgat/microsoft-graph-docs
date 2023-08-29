---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW FOR THE KIOTA BASED SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($requestAdapter);

$requestConfiguration = new CalendarViewRequestBuilderGetRequestConfiguration();

$queryParameters = new CalendarViewRequestBuilderGetQueryParameters();
$queryParameters->start = "2018-04-30T00:00:00Z";
$queryParameters->end = "2018-05-10T00:00:00Z";

$requestConfiguration->queryParameters = $queryParameters;


$requestResult = $graphServiceClient->bookingBusinessesById('bookingBusiness-id')->calendarView()->get($requestConfiguration);


```