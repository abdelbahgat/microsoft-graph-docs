---
title: "mobileAppIntent enum type"
description: "Indicates the status of the mobile app on the device."
author: "jaiprakashmb"
ms.localizationpriority: medium
ms.prod: "intune"
doc_type: enumPageType
---

# mobileAppIntent enum type

Namespace: microsoft.graph

> **Note:** The Microsoft Graph API for Intune requires an [active Intune license](https://go.microsoft.com/fwlink/?linkid=839381) for the tenant.

Indicates the status of the mobile app on the device.

## Members
|Member|Value|Description|
|:---|:---|:---|
|available|0|Available|
|notAvailable|1|Not Available|
|requiredInstall|2|Required Install|
|requiredUninstall|3|Required Uninstall|
|requiredAndAvailableInstall|4|RequiredAndAvailableInstall|
|availableInstallWithoutEnrollment|5|AvailableInstallWithoutEnrollment|
|exclude|6|Exclude|
