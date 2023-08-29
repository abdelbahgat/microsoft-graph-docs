---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

const settings = {
    deletedUserPersonalSiteRetentionPeriodInDays: 365,
    excludedFileExtensionsForSyncApp: ['.mp3'],
    imageTaggingOption: 'enhanced',
    isSitesStorageLimitAutomatic: false,
    isSyncButtonHiddenOnPersonalSite: false,
    isUnmanagedSyncAppForTenantRestricted: false,
    personalSiteDefaultStorageLimitInMB: 120000
};

await client.api('/admin/sharepoint/settings')
	.version('beta')
	.update(settings);

```