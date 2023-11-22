---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestConfiguration = new ThreatAssessmentRequestItemRequestBuilderGetRequestConfiguration();
$queryParameters = ThreatAssessmentRequestItemRequestBuilderGetRequestConfiguration::createQueryParameters();
$queryParameters->expand = ["results"];
$requestConfiguration->queryParameters = $queryParameters;


$result = $graphServiceClient->informationProtection()->threatAssessmentRequests()->byThreatAssessmentRequestId('threatAssessmentRequest-id')->get($requestConfiguration)->wait();

```