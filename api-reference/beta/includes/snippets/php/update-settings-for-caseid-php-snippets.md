---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new CaseSettings();
$redundancyDetection = new RedundancyDetectionSettings();
$redundancyDetection->setIsEnabled(false);
$redundancyDetection->setSimilarityThreshold(70);
$redundancyDetection->setMinWords(12);
$redundancyDetection->setMaxWords(400000);
$requestBody->setRedundancyDetection($redundancyDetection);
$topicModeling = new TopicModelingSettings();
$topicModeling->setIsEnabled(false);
$topicModeling->setIgnoreNumbers(false);
$topicModeling->setTopicCount(50);
$topicModeling->setDynamicallyAdjustTopicCount(false);
$requestBody->setTopicModeling($topicModeling);
$ocr = new OcrSettings();
$ocr->setIsEnabled(true);
$ocr->setMaxImageSize(12000);
$requestBody->setOcr($ocr);

$result = $graphServiceClient->compliance()->ediscovery()->cases()->byCaseId('case-id')->settings()->patch($requestBody)->wait();

```