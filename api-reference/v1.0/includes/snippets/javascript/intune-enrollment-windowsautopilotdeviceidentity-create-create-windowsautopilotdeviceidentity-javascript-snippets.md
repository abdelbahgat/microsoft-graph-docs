---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

const windowsAutopilotDeviceIdentity = {
  '@odata.type': '#microsoft.graph.windowsAutopilotDeviceIdentity',
  groupTag: 'Group Tag value',
  purchaseOrderIdentifier: 'Purchase Order Identifier value',
  serialNumber: 'Serial Number value',
  productKey: 'Product Key value',
  manufacturer: 'Manufacturer value',
  model: 'Model value',
  enrollmentState: 'enrolled',
  lastContactedDateTime: '2016-12-31T23:58:44.2908994-08:00',
  addressableUserName: 'Addressable User Name value',
  userPrincipalName: 'User Principal Name value',
  resourceName: 'Resource Name value',
  skuNumber: 'Sku Number value',
  systemFamily: 'System Family value',
  azureActiveDirectoryDeviceId: 'Azure Active Directory Device Id value',
  managedDeviceId: 'Managed Device Id value',
  displayName: 'Display Name value'
};

await client.api('/deviceManagement/windowsAutopilotDeviceIdentities')
	.post(windowsAutopilotDeviceIdentity);

```