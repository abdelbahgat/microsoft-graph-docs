---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new AuthenticationConditionApplication();
$requestBody->setOdataType('#microsoft.graph.authenticationConditionApplication');
$requestBody->setAppId('63856651-13d9-4784-9abf-20758d509e19');

$result = $graphServiceClient->identity()->authenticationEventsFlows()->byAuthenticationEventsFlowId('authenticationEventsFlow-id')->conditions()->applications()->includeApplications()->post($requestBody)->wait();

```