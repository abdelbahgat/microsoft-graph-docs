---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW FOR THE KIOTA BASED SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($requestAdapter);

$requestBody = new EvaluateClassificationResultsPostRequestBody();
$contentInfo = new ContentInfo();
$contentInfo->set@odatatype('#microsoft.graph.contentInfo');

$contentInfo->setFormat(new ContentFormat('default'));

$ContentInfo->setIdentifier(null);

$contentInfo->setState(new ContentState('rest'));

$additionalData = [
'format@odata.type' => '#microsoft.graph.contentFormat', 
'state@odata.type' => '#microsoft.graph.contentState', 
];
$contentInfo->setAdditionalData($additionalData);



$requestBody->setContentInfo($contentInfo);
$classificationResultsClassificationResult1 = new ClassificationResult();
$additionalData = [
'sensitiveTypeId' => 'cb353f78-2b72-4c3c-8827-92ebe4f69fdf', 
'count' => 4,
'confidenceLevel' => 75,
];
$classificationResultsClassificationResult1->setAdditionalData($additionalData);



$classificationResultsArray []= $classificationResultsClassificationResult1;
$requestBody->setClassificationResults($classificationResultsArray);



$requestConfiguration = new EvaluateClassificationResultsRequestBuilderPostRequestConfiguration();

$headers = [
'User-Agent' => 'ContosoLOBApp/1.0',
];

$requestConfiguration->headers = $headers;


$requestResult = $graphServiceClient->informationProtection()->policy()->labels()->evaluateClassificationResults()->post($requestBody, $requestConfiguration);


```