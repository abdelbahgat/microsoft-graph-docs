---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW FOR THE KIOTA BASED SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($requestAdapter);

$requestBody = new B2xIdentityUserFlow();
$requestBody->setId('UserFlowWithAPIConnector');

$requestBody->setUserFlowType(new UserFlowType('signuporsignin'));

$requestBody->setUserFlowTypeVersion(userFlowTypeVersion);

$apiConnectorConfiguration = new UserFlowApiConnectorConfiguration();
$apiConnectorConfigurationPostFederationSignup = new PostFederationSignup();
$additionalData = [
'@odata.id' => 'https://graph.microsoft.com/v1/identity/apiConnectors/{id}', 
];
$apiConnectorConfigurationPostFederationSignup->setAdditionalData($additionalData);



$apiConnectorConfiguration->setPostFederationSignup($apiConnectorConfigurationPostFederationSignup);
$apiConnectorConfigurationPostAttributeCollection = new PostAttributeCollection();
$additionalData = [
'@odata.id' => 'https://graph.microsoft.com/v1/identity/apiConnectors/{id}', 
];
$apiConnectorConfigurationPostAttributeCollection->setAdditionalData($additionalData);



$apiConnectorConfiguration->setPostAttributeCollection($apiConnectorConfigurationPostAttributeCollection);

$requestBody->setApiConnectorConfiguration($apiConnectorConfiguration);


$requestResult = $graphServiceClient->identity()->b2xUserFlows()->post($requestBody);


```