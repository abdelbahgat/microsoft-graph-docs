---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new AndroidStoreApp();
$requestBody->setOdataType('#microsoft.graph.androidStoreApp');
$requestBody->setDisplayName('Display Name value');
$requestBody->setDescription('Description value');
$requestBody->setPublisher('Publisher value');
$largeIcon = new MimeContent();
$largeIcon->setOdataType('microsoft.graph.mimeContent');
$largeIcon->setType('Type value');
$largeIcon->setValue(\GuzzleHttp\Psr7\Utils::streamFor(base64_decode('dmFsdWU=')));
$requestBody->setLargeIcon($largeIcon);
$requestBody->setIsFeatured(true);
$requestBody->setPrivacyInformationUrl('https://example.com/privacyInformationUrl/');
$requestBody->setInformationUrl('https://example.com/informationUrl/');
$requestBody->setOwner('Owner value');
$requestBody->setDeveloper('Developer value');
$requestBody->setNotes('Notes value');
$requestBody->setPublishingState(new MobileAppPublishingState('processing'));
$requestBody->setPackageId('Package Id value');
$requestBody->setAppStoreUrl('https://example.com/appStoreUrl/');
$minimumSupportedOperatingSystem = new AndroidMinimumOperatingSystem();
$minimumSupportedOperatingSystem->setOdataType('microsoft.graph.androidMinimumOperatingSystem');
$minimumSupportedOperatingSystem->setV40(true);
$minimumSupportedOperatingSystem->setV403(true);
$minimumSupportedOperatingSystem->setV41(true);
$minimumSupportedOperatingSystem->setV42(true);
$minimumSupportedOperatingSystem->setV43(true);
$minimumSupportedOperatingSystem->setV44(true);
$minimumSupportedOperatingSystem->setV50(true);
$minimumSupportedOperatingSystem->setV51(true);
$minimumSupportedOperatingSystem->setV60(true);
$minimumSupportedOperatingSystem->setV70(true);
$minimumSupportedOperatingSystem->setV71(true);
$minimumSupportedOperatingSystem->setV80(true);
$minimumSupportedOperatingSystem->setV81(true);
$minimumSupportedOperatingSystem->setV90(true);
$minimumSupportedOperatingSystem->setV100(true);
$minimumSupportedOperatingSystem->setV110(true);
$requestBody->setMinimumSupportedOperatingSystem($minimumSupportedOperatingSystem);

$result = $graphServiceClient->deviceAppManagement()->mobileApps()->post($requestBody)->wait();

```