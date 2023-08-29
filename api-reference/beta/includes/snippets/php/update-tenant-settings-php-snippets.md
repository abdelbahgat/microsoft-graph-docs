---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW FOR THE KIOTA BASED SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($requestAdapter);

$requestBody = new Settings();
$requestBody->setDeletedUserPersonalSiteRetentionPeriodInDays(deletedUserPersonalSiteRetentionPeriodInDays);

$requestBody->setExcludedFileExtensionsForSyncApp(['.mp3', ]);

$requestBody->setImageTaggingOption(new ImageTaggingChoice('enhanced'));

$requestBody->setIsSitesStorageLimitAutomatic(false);

$requestBody->setIsSyncButtonHiddenOnPersonalSite(false);

$requestBody->setIsUnmanagedSyncAppForTenantRestricted(false);

$requestBody->setPersonalSiteDefaultStorageLimitInMB(personalSiteDefaultStorageLimitInMB);



$graphServiceClient->admin()->sharepoint()->settings()->patch($requestBody);


```