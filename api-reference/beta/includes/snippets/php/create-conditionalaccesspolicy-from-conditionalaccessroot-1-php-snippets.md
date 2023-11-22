---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new ConditionalAccessPolicy();
$requestBody->setDisplayName('Access to EXO requires MFA');
$requestBody->setState(new ConditionalAccessPolicyState('enabled'));
$conditions = new ConditionalAccessConditionSet();
$conditions->setClientAppTypes([new ConditionalAccessClientApp('mobileAppsAndDesktopClients'),new ConditionalAccessClientApp('browser'),	]);
$conditionsApplications = new ConditionalAccessApplications();
$conditionsApplications->setIncludeApplications(['00000002-0000-0ff1-ce00-000000000000', 	]);
$conditions->setApplications($conditionsApplications);
$conditionsUsers = new ConditionalAccessUsers();
$conditionsUsers->setIncludeGroups(['ba8e7ded-8b0f-4836-ba06-8ff1ecc5c8ba', 	]);
$conditions->setUsers($conditionsUsers);
$conditionsLocations = new ConditionalAccessLocations();
$conditionsLocations->setIncludeLocations(['All', 	]);
$conditionsLocations->setExcludeLocations(['AllTrusted', 	]);
$conditions->setLocations($conditionsLocations);
$requestBody->setConditions($conditions);
$grantControls = new ConditionalAccessGrantControls();
$grantControls->setOperator('OR');
$grantControls->setBuiltInControls([new ConditionalAccessGrantControl('mfa'),	]);
$requestBody->setGrantControls($grantControls);

$result = $graphServiceClient->identity()->conditionalAccess()->policies()->post($requestBody)->wait();

```