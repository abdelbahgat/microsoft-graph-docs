---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW FOR THE KIOTA BASED SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($requestAdapter);

$requestBody = new B2cIdentityUserFlow();
$requestBody->setId('Customer');

$requestBody->setUserFlowType(new UserFlowType('signuporsignin'));

$requestBody->setUserFlowTypeVersion(userFlowTypeVersion);

$identityProvidersIdentityProvider1 = new IdentityProvider();
$identityProvidersIdentityProvider1->setId('Facebook-OAuth');


$identityProvidersArray []= $identityProvidersIdentityProvider1;
$requestBody->setIdentityProviders($identityProvidersArray);



$requestConfiguration = new B2cUserFlowsRequestBuilderPostRequestConfiguration();

$headers = [
'Location' => 'https://graph.microsoft.com/beta/identity/b2cUserFlows(\'B2C_1_Customer\')',
];

$requestConfiguration->headers = $headers;


$requestResult = $graphServiceClient->identity()->b2cUserFlows()->post($requestBody, $requestConfiguration);


```