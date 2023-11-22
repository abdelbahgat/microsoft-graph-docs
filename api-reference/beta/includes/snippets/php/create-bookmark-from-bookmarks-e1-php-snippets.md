---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new Bookmark();
$requestBody->setDisplayName('Contoso Install Site');
$requestBody->setWebUrl('http://www.contoso.com/');
$requestBody->setDescription('Try or buy Contoso for Home or Business and view product information');
$keywords = new AnswerKeyword();
$keywords->setKeywords(['Contoso', 'install', 	]);
$keywords->setReservedKeywords(['Contoso', 	]);
$keywords->setMatchSimilarKeywords(true);
$requestBody->setKeywords($keywords);
$requestBody->setAvailabilityStartDateTime(null);
$requestBody->setAvailabilityEndDateTime(null);
$requestBody->setPlatforms([new DevicePlatformType('windows'),	]);
$targetedVariationsAnswerVariant1 = new AnswerVariant();
$targetedVariationsAnswerVariant1->setLanguageTag('es-es');
$targetedVariationsAnswerVariant1->setDisplayName('Sitio de instalación Contoso');
$targetedVariationsAnswerVariant1->setDescription('Pruebe o compre Contoso hogar o negocios y vea la información del producto');
$targetedVariationsArray []= $targetedVariationsAnswerVariant1;
$requestBody->setTargetedVariations($targetedVariationsArray);

$requestBody->setState(new AnswerState('published'));

$result = $graphServiceClient->search()->bookmarks()->post($requestBody)->wait();

```