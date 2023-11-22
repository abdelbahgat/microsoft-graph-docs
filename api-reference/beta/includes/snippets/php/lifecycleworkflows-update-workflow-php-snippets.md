---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new Workflow();
$requestBody->setDescription('Configure new hire tasks for onboarding employees on their first day');
$requestBody->setDisplayName('Australia Onboard new hire employee');
$requestBody->setIsEnabled(true);
$requestBody->setIsSchedulingEnabled(false);

$result = $graphServiceClient->identityGovernance()->lifecycleWorkflows()->workflows()->byWorkflowId('workflow-id')->patch($requestBody)->wait();

```