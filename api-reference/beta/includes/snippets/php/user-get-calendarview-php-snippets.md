---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestConfiguration = new CalendarViewRequestBuilderGetRequestConfiguration();
$queryParameters = CalendarViewRequestBuilderGetRequestConfiguration::createQueryParameters();
$queryParameters->startDateTime = "2020-01-01T19:00:00-08:00";
$queryParameters->endDateTime = "2020-01-02T19:00:00-08:00";
$requestConfiguration->queryParameters = $queryParameters;


$result = $graphServiceClient->me()->calendarView()->get($requestConfiguration)->wait();

```