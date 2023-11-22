---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new VppToken();
$requestBody->setOdataType('#microsoft.graph.vppToken');
$requestBody->setOrganizationName('Organization Name value');
$requestBody->setVppTokenAccountType(new VppTokenAccountType('education'));
$requestBody->setAppleId('Apple Id value');
$requestBody->setExpirationDateTime(new \DateTime('2016-12-31T23:57:57.2481234-08:00'));
$requestBody->setLastSyncDateTime(new \DateTime('2017-01-01T00:02:49.3205976-08:00'));
$requestBody->setToken('Token value');
$requestBody->setState(new VppTokenState('valid'));
$requestBody->setLastSyncStatus(new VppTokenSyncStatus('inProgress'));
$requestBody->setAutomaticallyUpdateApps(true);
$requestBody->setCountryOrRegion('Country Or Region value');

$result = $graphServiceClient->deviceAppManagement()->vppTokens()->post($requestBody)->wait();

```