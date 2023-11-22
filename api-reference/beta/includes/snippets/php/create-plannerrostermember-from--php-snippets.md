---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new PlannerRosterMember();
$requestBody->setOdataType('#microsoft.graph.plannerRosterMember');
$requestBody->setUserId('String');

$result = $graphServiceClient->planner()->rosters()->byPlannerRosterId('plannerRoster-id')->members()->post($requestBody)->wait();

```