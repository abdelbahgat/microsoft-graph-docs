---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new EducationAssignmentSettings();
$requestBody->setSubmissionAnimationDisabled(true);

$result = $graphServiceClient->education()->classes()->byEducationClassId('educationClass-id')->assignmentSettings()->patch($requestBody)->wait();

```