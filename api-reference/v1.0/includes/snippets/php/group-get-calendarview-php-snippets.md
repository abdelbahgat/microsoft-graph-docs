---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestConfiguration = new CalendarViewRequestBuilderGetRequestConfiguration();
$headers = [
		'Prefer' => 'outlook.body-content-type="text"',
	];
$requestConfiguration->headers = $headers;

$queryParameters = CalendarViewRequestBuilderGetRequestConfiguration::createQueryParameters();
$queryParameters->startDateTime = "2017-01-01T19:00:00-08:00";
$queryParameters->endDateTime = "2017-10-01T19:00:00.00-08:00";
$requestConfiguration->queryParameters = $queryParameters;


$result = $graphServiceClient->groups()->byGroupId('group-id')->calendarView()->get($requestConfiguration)->wait();

```