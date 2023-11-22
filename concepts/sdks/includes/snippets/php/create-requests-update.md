<!-- markdownlint-disable MD041 -->

```php
<?php

$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new Event();
$requestBody->setOriginalStartTimeZone('originalStartTimeZone-value');

$requestBody->setOriginalEndTimeZone('originalEndTimeZone-value');

$responseStatus = new ResponseStatus();
$responseStatus->setResponse(new ResponseType('none'));

$responseStatus->setTime(new \DateTime('datetime-value'));


$requestBody->setResponseStatus($responseStatus);
$requestBody->setRecurrence(null);

$requestBody->setReminderMinutesBeforeStart(99);

$requestBody->setIsOnlineMeeting(true);

$requestBody->setOnlineMeetingProvider(new OnlineMeetingProviderType('teamsForBusiness'));

$requestBody->setIsReminderOn(true);

$requestBody->setHideAttendees(false);

$requestBody->setCategories(['Red category', 	]);

$result = $graphServiceClient->me()->events()->byEventId('event-id')->patch($requestBody);
```
