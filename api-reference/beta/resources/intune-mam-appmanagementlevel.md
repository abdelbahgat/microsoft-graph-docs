---
title: "appManagementLevel enum type"
description: "Management levels for apps"
author: "jaiprakashmb"
localization_priority: Normal
ms.prod: "intune"
doc_type: enumPageType
---

# appManagementLevel enum type

Namespace: microsoft.graph

> **Important:** Microsoft Graph APIs under the /beta version are subject to change; production use is not supported.

> **Note:** The Microsoft Graph API for Intune requires an [active Intune license](https://go.microsoft.com/fwlink/?linkid=839381) for the tenant.

Management levels for apps

## Members
|Member|Value|Description|
|:---|:---|:---|
|unspecified|0|Unspecified|
|unmanaged|1|Unmanaged|
|mdm|2|MDM|
|androidEnterprise|4|Android Enterprise|
|androidEnterpriseDedicatedDevicesWithAzureAdSharedMode|8|Android Enterprise dedicated devices with Azure AD Shared mode|
|androidOpenSourceProjectUserAssociated|16|Android Open Source Project (AOSP) devices|
|androidOpenSourceProjectUserless|32|Android Open Source Project (AOSP) userless devices|
|unknownFutureValue|64|Place holder for evolvable enum|
