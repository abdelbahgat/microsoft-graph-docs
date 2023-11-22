---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new B2cIdentityUserFlow();
$requestBody->setId('UserFlowWithAPIConnector');
$requestBody->setUserFlowType(new UserFlowType('signUpOrSignIn'));
$requestBody->setUserFlowTypeVersion(1);
$apiConnectorConfiguration = new UserFlowApiConnectorConfiguration();
$apiConnectorConfigurationPostFederationSignup = new IdentityApiConnector();
$additionalData = [
	'@odata.id' => '{apiConnectorId}',
];
$apiConnectorConfigurationPostFederationSignup->setAdditionalData($additionalData);
$apiConnectorConfiguration->setPostFederationSignup($apiConnectorConfigurationPostFederationSignup);
$apiConnectorConfigurationPostAttributeCollection = new IdentityApiConnector();
$additionalData = [
	'@odata.id' => '{apiConnectorId}',
];
$apiConnectorConfigurationPostAttributeCollection->setAdditionalData($additionalData);
$apiConnectorConfiguration->setPostAttributeCollection($apiConnectorConfigurationPostAttributeCollection);
$requestBody->setApiConnectorConfiguration($apiConnectorConfiguration);

$result = $graphServiceClient->identity()->b2cUserFlows()->post($requestBody)->wait();

```