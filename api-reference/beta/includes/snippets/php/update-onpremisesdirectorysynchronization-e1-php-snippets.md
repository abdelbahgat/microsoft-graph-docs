---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new OnPremisesDirectorySynchronization();
$configuration = new OnPremisesDirectorySynchronizationConfiguration();
$configurationAccidentalDeletionPrevention = new OnPremisesAccidentalDeletionPrevention();
$configurationAccidentalDeletionPrevention->setSynchronizationPreventionType(new OnPremisesDirectorySynchronizationDeletionPreventionType('enabledForCount'));
$configurationAccidentalDeletionPrevention->setAlertThreshold(500);
$configuration->setAccidentalDeletionPrevention($configurationAccidentalDeletionPrevention);
$configuration->setSynchronizationInterval(new \DateInterval('PT30M'));
$configuration->setCustomerRequestedSynchronizationInterval(new \DateInterval('PT1H'));
$requestBody->setConfiguration($configuration);
$features = new OnPremisesDirectorySynchronizationFeature();
$features->setGroupWriteBackEnabled(true);
$requestBody->setFeatures($features);

$result = $graphServiceClient->directory()->onPremisesSynchronization()->byOnPremisesDirectorySynchronizationId('onPremisesDirectorySynchronization-id')->patch($requestBody)->wait();

```