---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new PlannerPlanConfigurationLocalization();
$requestBody->setOdataType('#microsoft.graph.plannerPlanConfigurationLocalization');
$requestBody->setPlanTitle('Order Tracking');
$bucketsPlannerPlanConfigurationBucketLocalization1 = new PlannerPlanConfigurationBucketLocalization();
$bucketsPlannerPlanConfigurationBucketLocalization1->setExternalBucketId('deliveryBucket');
$bucketsPlannerPlanConfigurationBucketLocalization1->setName('Deliveries');
$bucketsArray []= $bucketsPlannerPlanConfigurationBucketLocalization1;
$bucketsPlannerPlanConfigurationBucketLocalization2 = new PlannerPlanConfigurationBucketLocalization();
$bucketsPlannerPlanConfigurationBucketLocalization2->setExternalBucketId('storePickupBucket');
$bucketsPlannerPlanConfigurationBucketLocalization2->setName('Pickup');
$bucketsArray []= $bucketsPlannerPlanConfigurationBucketLocalization2;
$bucketsPlannerPlanConfigurationBucketLocalization3 = new PlannerPlanConfigurationBucketLocalization();
$bucketsPlannerPlanConfigurationBucketLocalization3->setExternalBucketId('specialOrdersBucket');
$bucketsPlannerPlanConfigurationBucketLocalization3->setName('Special Orders');
$bucketsArray []= $bucketsPlannerPlanConfigurationBucketLocalization3;
$bucketsPlannerPlanConfigurationBucketLocalization4 = new PlannerPlanConfigurationBucketLocalization();
$bucketsPlannerPlanConfigurationBucketLocalization4->setExternalBucketId('returnProcessingBucket');
$bucketsPlannerPlanConfigurationBucketLocalization4->setName('Customer Returns');
$bucketsArray []= $bucketsPlannerPlanConfigurationBucketLocalization4;
$requestBody->setBuckets($bucketsArray);


$result = $graphServiceClient->solutions()->businessScenarios()->byBusinessScenarioId('businessScenario-id')->planner()->planConfiguration()->localizations()->byPlannerPlanConfigurationLocalizationId('plannerPlanConfigurationLocalization-id')->patch($requestBody)->wait();

```