---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new PlannerAssignedToTaskBoardTaskFormat();
$orderHintsByAssignee = new PlannerOrderHintsByAssignee();
$additionalData = [
	'aaa27244-1db4-476a-a5cb-004607466324' => '8566473P 957764Jk!',
];
$orderHintsByAssignee->setAdditionalData($additionalData);
$requestBody->setOrderHintsByAssignee($orderHintsByAssignee);
$requestConfiguration = new AssignedToTaskBoardFormatRequestBuilderPatchRequestConfiguration();
$headers = [
		'Prefer' => 'return=representation',
		'If-Match' => 'W/"JzEtVGFzayAgQEBAQEBAQEBAQEBAQEBAWCc="',
	];
$requestConfiguration->headers = $headers;


$result = $graphServiceClient->planner()->tasks()->byPlannerTaskId('plannerTask-id')->assignedToTaskBoardFormat()->patch($requestBody, $requestConfiguration)->wait();

```