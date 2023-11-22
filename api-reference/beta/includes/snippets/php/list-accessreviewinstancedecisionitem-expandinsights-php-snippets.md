---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestConfiguration = new DecisionsRequestBuilderGetRequestConfiguration();
$queryParameters = DecisionsRequestBuilderGetRequestConfiguration::createQueryParameters();
$queryParameters->expand = ["insights"];
$requestConfiguration->queryParameters = $queryParameters;


$result = $graphServiceClient->identityGovernance()->accessReviews()->definitions()->byAccessReviewScheduleDefinitionId('accessReviewScheduleDefinition-id')->instances()->byAccessReviewInstanceId('accessReviewInstance-id')->decisions()->get($requestConfiguration)->wait();

```