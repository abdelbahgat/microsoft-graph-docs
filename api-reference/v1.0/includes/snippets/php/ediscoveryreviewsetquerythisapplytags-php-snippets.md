---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW FOR THE KIOTA BASED SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($requestAdapter);

$requestBody = new ApplyTagsPostRequestBody();
$tagsToAdd1 = new ();
$additionalData = [
'id' => 'd3d99dc704a74801b792b3e1e722aa0d', 
];
$tagsToAdd1->setAdditionalData($additionalData);



$tagsToAddArray []= $tagsToAdd1;
$requestBody->setTagsToAdd($tagsToAddArray);




$graphServiceClient->security()->cases()->ediscoveryCasesById('ediscoveryCase-id')->reviewSetsById('ediscoveryReviewSet-id')->queriesById('ediscoveryReviewSetQuery-id')->applyTags()->post($requestBody);


```