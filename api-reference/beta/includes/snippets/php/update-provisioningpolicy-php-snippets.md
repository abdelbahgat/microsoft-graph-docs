---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new CloudPcProvisioningPolicy();
$requestBody->setOdataType('#microsoft.graph.cloudPcProvisioningPolicy');
$requestBody->setDisplayName('HR provisioning policy');
$requestBody->setDescription('Provisioning policy for India HR employees');
$requestBody->setOnPremisesConnectionId('4e47d0f6-6f77-44f0-8893-c0fe1701ffff');
$requestBody->setImageId('Image ID value');
$requestBody->setImageDisplayName('Image Display Name value');
$requestBody->setImageType(new CloudPcProvisioningPolicyImageType('custom'));
$windowsSettings = new CloudPcWindowsSettings();
$windowsSettings->setLanguage('en-US');
$requestBody->setWindowsSettings($windowsSettings);

$result = $graphServiceClient->deviceManagement()->virtualEndpoint()->provisioningPolicies()->byCloudPcProvisioningPolicyId('cloudPcProvisioningPolicy-id')->patch($requestBody)->wait();

```