---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

const androidManagedAppProtection = {
  '@odata.type': '#microsoft.graph.androidManagedAppProtection',
  displayName: 'Display Name value',
  description: 'Description value',
  version: 'Version value',
  periodOfflineBeforeAccessCheck: '-PT17.1357909S',
  periodOnlineBeforeAccessCheck: 'PT35.0018757S',
  allowedInboundDataTransferSources: 'managedApps',
  allowedOutboundDataTransferDestinations: 'managedApps',
  organizationalCredentialsRequired: true,
  allowedOutboundClipboardSharingLevel: 'managedAppsWithPasteIn',
  dataBackupBlocked: true,
  deviceComplianceRequired: true,
  managedBrowserToOpenLinksRequired: true,
  saveAsBlocked: true,
  periodOfflineBeforeWipeIsEnforced: '-PT3M22.1587532S',
  pinRequired: true,
  maximumPinRetries: 1,
  simplePinBlocked: true,
  minimumPinLength: 0,
  pinCharacterSet: 'alphanumericAndSymbol',
  periodBeforePinReset: 'PT3M29.6631862S',
  allowedDataStorageLocations: [
    'sharePoint'
  ],
  contactSyncBlocked: true,
  printBlocked: true,
  fingerprintBlocked: true,
  disableAppPinIfDevicePinIsSet: true,
  minimumRequiredOsVersion: 'Minimum Required Os Version value',
  minimumWarningOsVersion: 'Minimum Warning Os Version value',
  minimumRequiredAppVersion: 'Minimum Required App Version value',
  minimumWarningAppVersion: 'Minimum Warning App Version value',
  managedBrowser: 'microsoftEdge',
  isAssigned: true,
  screenCaptureBlocked: true,
  disableAppEncryptionIfDeviceEncryptionIsEnabled: true,
  encryptAppData: true,
  deployedAppCount: 0,
  minimumRequiredPatchVersion: 'Minimum Required Patch Version value',
  minimumWarningPatchVersion: 'Minimum Warning Patch Version value',
  customBrowserPackageId: 'Custom Browser Package Id value',
  customBrowserDisplayName: 'Custom Browser Display Name value'
};

await client.api('/deviceAppManagement/androidManagedAppProtections/{androidManagedAppProtectionId}')
	.update(androidManagedAppProtection);

```