---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new AccessPackageAssignmentPolicy();
$requestBody->setId('4540a08f-8ab5-43f6-a923-015275799197');
$requestBody->setDisplayName('policy with custom access package workflow extension');
$requestBody->setDescription('Run specified custom access package workflow extension at different stages.');
$requestBody->setAccessPackageId('ba5807c7-2aa9-4c8a-907e-4a17ee587500');
$requestBody->setRequestApprovalSettings(null);
$requestorSettings = new RequestorSettings();
$requestorSettings->setAcceptRequests(true);
$requestorSettings->setScopeType('AllExistingDirectorySubjects');
$requestorSettings->setAllowedRequestors([	]);
$requestBody->setRequestorSettings($requestorSettings);
$requestBody->setAccessReviewSettings(null);
$requestBody->setCustomExtensionHandlers([	]);
$additionalData = [
	'expiration' => [
		'type' => 'afterDuration',
		'duration' => 'P365D',
	],
];
$requestBody->setAdditionalData($additionalData);

$result = $graphServiceClient->identityGovernance()->entitlementManagement()->accessPackageAssignmentPolicies()->byAccessPackageAssignmentPolicyId('accessPackageAssignmentPolicy-id')->put($requestBody)->wait();

```