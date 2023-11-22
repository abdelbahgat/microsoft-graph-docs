---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new B2xIdentityUserFlow();
$requestBody->setId('UserFlowWithAPIConnector');
$requestBody->setUserFlowType(new UserFlowType('signUpOrSignIn'));
$requestBody->setUserFlowTypeVersion(1);
$apiConnectorConfiguration = new UserFlowApiConnectorConfiguration();
$apiConnectorConfigurationPostFederationSignup = new IdentityApiConnector();
$additionalData = [
	'@odata.id' => 'https://graph.microsoft.com/v1/identity/apiConnectors/{id}',
];
$apiConnectorConfigurationPostFederationSignup->setAdditionalData($additionalData);
$apiConnectorConfiguration->setPostFederationSignup($apiConnectorConfigurationPostFederationSignup);
$apiConnectorConfigurationPostAttributeCollection = new IdentityApiConnector();
$additionalData = [
	'@odata.id' => 'https://graph.microsoft.com/v1/identity/apiConnectors/{id}',
];
$apiConnectorConfigurationPostAttributeCollection->setAdditionalData($additionalData);
$apiConnectorConfiguration->setPostAttributeCollection($apiConnectorConfigurationPostAttributeCollection);
$requestBody->setApiConnectorConfiguration($apiConnectorConfiguration);

$result = $graphServiceClient->identity()->b2xUserFlows()->post($requestBody)->wait();

```