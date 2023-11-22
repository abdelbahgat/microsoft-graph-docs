---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

const deviceAppManagement = {
  '@odata.type': '#microsoft.graph.deviceAppManagement',
  microsoftStoreForBusinessLastSuccessfulSyncDateTime: '2016-12-31T23:57:45.2453148-08:00',
  isEnabledForMicrosoftStoreForBusiness: true,
  microsoftStoreForBusinessLanguage: 'Microsoft Store For Business Language value',
  microsoftStoreForBusinessLastCompletedApplicationSyncTime: '2017-01-01T00:02:00.0421137-08:00'
};

await client.api('/deviceAppManagement')
	.update(deviceAppManagement);

```