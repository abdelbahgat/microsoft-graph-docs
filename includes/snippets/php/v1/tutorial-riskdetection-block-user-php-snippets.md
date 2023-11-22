---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new ConditionalAccessPolicy();
$requestBody->setDisplayName('Policy for risky sign-in block access');
$requestBody->setState(new ConditionalAccessPolicyState('enabled'));
$conditions = new ConditionalAccessConditionSet();
$conditions->setSignInRiskLevels([new RiskLevel('high'),new RiskLevel('medium'),	]);
$conditionsApplications = new ConditionalAccessApplications();
$conditionsApplications->setIncludeApplications(['All', 	]);
$conditions->setApplications($conditionsApplications);
$conditionsUsers = new ConditionalAccessUsers();
$conditionsUsers->setIncludeUsers(['4628e7df-dff3-407c-a08f-75f08c0806dc', 	]);
$conditions->setUsers($conditionsUsers);
$requestBody->setConditions($conditions);
$grantControls = new ConditionalAccessGrantControls();
$grantControls->setOperator('OR');
$grantControls->setBuiltInControls([new ConditionalAccessGrantControl('block'),	]);
$requestBody->setGrantControls($grantControls);

$result = $graphServiceClient->identity()->conditionalAccess()->policies()->post($requestBody)->wait();

```