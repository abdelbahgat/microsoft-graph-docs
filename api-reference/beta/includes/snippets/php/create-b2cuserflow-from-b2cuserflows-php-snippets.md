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



$requestResult = $graphServiceClient->identity()->b2cUserFlows()->post($requestBody);


```