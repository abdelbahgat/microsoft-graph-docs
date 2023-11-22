---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new BatchRecordDecisionsPostRequestBody();
$requestBody->setDecision('Approve');
$requestBody->setJustification('All principals with access need continued access to the resource (Marketing Group) as all the principals are on the marketing team');
$requestBody->setResourceId('a5c51e59-3fcd-4a37-87a1-835c0c21488a');

$graphServiceClient->me()->pendingAccessReviewInstances()->byAccessReviewInstanceId('accessReviewInstance-id')->batchRecordDecisions()->post($requestBody)->wait();

```