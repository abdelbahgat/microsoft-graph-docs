---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW FOR THE KIOTA BASED SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($requestAdapter);

$requestConfiguration = new PlannerTaskRequestBuilderDeleteRequestConfiguration();

$headers = [
	'If-Match' => 'W/"JzEtVGFzayAgQEBAQEBAQEBAQEBAQEBAWCc="',
];

$requestConfiguration->headers = $headers;


$graphServiceClient->planner()->tasksById('plannerTask-id')->delete($requestConfiguration);


```