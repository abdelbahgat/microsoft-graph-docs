---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new CloudPcOrganizationSettings();
$requestBody->setOdataType('#microsoft.graph.cloudPcOrganizationSettings');
$requestBody->setEnableMEMAutoEnroll(true);
$requestBody->setOsVersion(new CloudPcOperatingSystem('windows11'));
$requestBody->setUserAccountType(new CloudPcUserAccountType('standardUser'));
$windowsSettings = new CloudPcWindowsSettings();
$windowsSettings->setLanguage('en-US');
$requestBody->setWindowsSettings($windowsSettings);

$result = $graphServiceClient->deviceManagement()->virtualEndpoint()->organizationSettings()->patch($requestBody)->wait();

```