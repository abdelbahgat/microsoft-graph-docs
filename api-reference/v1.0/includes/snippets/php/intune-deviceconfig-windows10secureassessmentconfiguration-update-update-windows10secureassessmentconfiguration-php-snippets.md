---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new Windows10SecureAssessmentConfiguration();
$requestBody->setOdataType('#microsoft.graph.windows10SecureAssessmentConfiguration');
$requestBody->setDescription('Description value');
$requestBody->setDisplayName('Display Name value');
$requestBody->setVersion(7);
$requestBody->setLaunchUri('Launch Uri value');
$requestBody->setConfigurationAccount('Configuration Account value');
$requestBody->setAllowPrinting(true);
$requestBody->setAllowScreenCapture(true);
$requestBody->setAllowTextSuggestion(true);

$result = $graphServiceClient->deviceManagement()->deviceConfigurations()->byDeviceConfigurationId('deviceConfiguration-id')->patch($requestBody)->wait();

```