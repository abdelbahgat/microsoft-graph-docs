---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new Schedule();
$requestBody->setEnabled(true);
$requestBody->setTimeZone('America/Chicago');
$requestBody->setProvisionStatus(new OperationStatus('completed'));
$requestBody->setProvisionStatusCode(null);
$requestBody->setOpenShiftsEnabled(true);
$requestBody->setSwapShiftsRequestsEnabled(true);
$requestBody->setOfferShiftRequestsEnabled(true);
$requestBody->setTimeOffRequestsEnabled(true);
$requestBody->setTimeClockEnabled(true);
$timeClockSettings = new TimeClockSettings();
$timeClockSettingsApprovedLocation = new GeoCoordinates();
$timeClockSettingsApprovedLocation->setAltitude(1024.13);
$timeClockSettingsApprovedLocation->setLatitude(26.13246);
$timeClockSettingsApprovedLocation->setLongitude(24.34616);
$timeClockSettings->setApprovedLocation($timeClockSettingsApprovedLocation);
$requestBody->setTimeClockSettings($timeClockSettings);

$result = $graphServiceClient->teams()->byTeamId('team-id')->schedule()->put($requestBody)->wait();

```