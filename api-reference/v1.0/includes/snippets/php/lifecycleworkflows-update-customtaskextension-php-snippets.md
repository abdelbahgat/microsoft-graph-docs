---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new CustomTaskExtension();
$requestBody->setDisplayName('Grant manager access to mailbox and OneDrive');
$requestBody->setDescription('Grant manager access to mailbox and OneDrive');
$endpointConfiguration = new LogicAppTriggerEndpointConfiguration();
$endpointConfiguration->setOdataType('#microsoft.graph.logicAppTriggerEndpointConfiguration');
$endpointConfiguration->setSubscriptionId('c500b67c-e9b7-4ad2-a90d-77d41385ae55');
$endpointConfiguration->setResourceGroupName('RG-LCM');
$endpointConfiguration->setLogicAppWorkflowName('ManagerAccess');
$requestBody->setEndpointConfiguration($endpointConfiguration);
$authenticationConfiguration = new AzureAdPopTokenAuthentication();
$authenticationConfiguration->setOdataType('#microsoft.graph.azureAdPopTokenAuthentication');
$requestBody->setAuthenticationConfiguration($authenticationConfiguration);
$clientConfiguration = new CustomExtensionClientConfiguration();
$clientConfiguration->setOdataType('#microsoft.graph.customExtensionClientConfiguration');
$clientConfiguration->setTimeoutInMilliseconds(1000);
$additionalData = [
	'maximumRetries' => 1,
];
$clientConfiguration->setAdditionalData($additionalData);
$requestBody->setClientConfiguration($clientConfiguration);
$callbackConfiguration = new CustomTaskExtensionCallbackConfiguration();
$callbackConfiguration->setOdataType('#microsoft.graph.identityGovernance.customTaskExtensionCallbackConfiguration');
$callbackConfiguration->setTimeoutDuration(new \DateInterval('PT20M'));
$requestBody->setCallbackConfiguration($callbackConfiguration);

$result = $graphServiceClient->identityGovernance()->lifecycleWorkflows()->customTaskExtensions()->byCustomTaskExtensionId('customTaskExtension-id')->patch($requestBody)->wait();

```