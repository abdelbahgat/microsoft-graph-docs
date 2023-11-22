---
description: "Automatically generated file. DO NOT MODIFY"
---

```bash

// THE CLI IS IN PREVIEW. NON-PRODUCTION USE ONLY
mgc device-app-management mobile-apps patch --mobile-app-id {mobileApp-id} --body '{\
  "@odata.type": "#microsoft.graph.managedIOSStoreApp",\
  "displayName": "Display Name value",\
  "description": "Description value",\
  "publisher": "Publisher value",\
  "largeIcon": {\
    "@odata.type": "microsoft.graph.mimeContent",\
    "type": "Type value",\
    "value": "dmFsdWU="\
  },\
  "isFeatured": true,\
  "privacyInformationUrl": "https://example.com/privacyInformationUrl/",\
  "informationUrl": "https://example.com/informationUrl/",\
  "owner": "Owner value",\
  "developer": "Developer value",\
  "notes": "Notes value",\
  "publishingState": "processing",\
  "appAvailability": "lineOfBusiness",\
  "version": "Version value",\
  "bundleId": "Bundle Id value",\
  "appStoreUrl": "https://example.com/appStoreUrl/",\
  "applicableDeviceType": {\
    "@odata.type": "microsoft.graph.iosDeviceType",\
    "iPad": true,\
    "iPhoneAndIPod": true\
  },\
  "minimumSupportedOperatingSystem": {\
    "@odata.type": "microsoft.graph.iosMinimumOperatingSystem",\
    "v8_0": true,\
    "v9_0": true,\
    "v10_0": true,\
    "v11_0": true,\
    "v12_0": true,\
    "v13_0": true,\
    "v14_0": true,\
    "v15_0": true\
  }\
}\
'

```