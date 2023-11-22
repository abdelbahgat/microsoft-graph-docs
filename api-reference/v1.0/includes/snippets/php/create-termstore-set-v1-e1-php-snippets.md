---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new Set();
$requestBody->setOdataType('#microsoft.graph.termStore.set');
$parentGroup = new Group();
$parentGroup->setId('fc733b51-10f1-40fd-b784-dc6d1e42804b');
$requestBody->setParentGroup($parentGroup);
$localizedNamesLocalizedName1 = new LocalizedName();
$localizedNamesLocalizedName1->setLanguageTag('en-US');
$localizedNamesLocalizedName1->setName('Department');
$localizedNamesArray []= $localizedNamesLocalizedName1;
$requestBody->setLocalizedNames($localizedNamesArray);


$result = $graphServiceClient->sites()->bySiteId('site-id')->termStore()->sets()->post($requestBody)->wait();

```