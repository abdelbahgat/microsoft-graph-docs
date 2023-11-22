---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

const managedAppRegistration = {
  '@odata.type': '#microsoft.graph.androidManagedAppRegistration',
  lastSyncDateTime: '2017-01-01T00:02:49.3205976-08:00',
  applicationVersion: 'Application Version value',
  managementSdkVersion: 'Management Sdk Version value',
  platformVersion: 'Platform Version value',
  deviceType: 'Device Type value',
  deviceTag: 'Device Tag value',
  deviceName: 'Device Name value',
  flaggedReasons: [
    'rootedDevice'
  ],
  userId: 'User Id value',
  appIdentifier: {
    '@odata.type': 'microsoft.graph.androidMobileAppIdentifier',
    packageId: 'Package Id value'
  },
  version: 'Version value'
};

await client.api('/deviceAppManagement/managedAppRegistrations')
	.post(managedAppRegistration);

```