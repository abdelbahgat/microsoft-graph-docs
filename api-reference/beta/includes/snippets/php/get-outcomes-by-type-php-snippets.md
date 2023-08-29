---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW FOR THE KIOTA BASED SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($requestAdapter);

$requestConfiguration = new OutcomesRequestBuilderGetRequestConfiguration();

$queryParameters = new OutcomesRequestBuilderGetQueryParameters();
$queryParameters->filter = "isof('microsoft.graph.educationFeedbackResourceOutcome')";

$requestConfiguration->queryParameters = $queryParameters;


$requestResult = $graphServiceClient->education()->classesById('educationClass-id')->assignmentsById('educationAssignment-id')->submissionsById('educationSubmission-id')->outcomes()->get($requestConfiguration);


```