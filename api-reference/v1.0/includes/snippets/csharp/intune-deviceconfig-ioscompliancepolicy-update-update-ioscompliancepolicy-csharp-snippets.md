---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

// Code snippets are only available for the latest version. Current version is 5.x

// Dependencies
using Microsoft.Graph.Models;

var requestBody = new IosCompliancePolicy
{
	OdataType = "#microsoft.graph.iosCompliancePolicy",
	Description = "Description value",
	DisplayName = "Display Name value",
	Version = 7,
	PasscodeBlockSimple = true,
	PasscodeExpirationDays = 6,
	PasscodeMinimumLength = 5,
	PasscodeMinutesOfInactivityBeforeLock = 5,
	PasscodePreviousPasscodeBlockCount = 2,
	PasscodeMinimumCharacterSetCount = 0,
	PasscodeRequiredType = RequiredPasswordType.Alphanumeric,
	PasscodeRequired = true,
	OsMinimumVersion = "Os Minimum Version value",
	OsMaximumVersion = "Os Maximum Version value",
	SecurityBlockJailbrokenDevices = true,
	DeviceThreatProtectionEnabled = true,
	DeviceThreatProtectionRequiredSecurityLevel = DeviceThreatProtectionLevel.Secured,
	ManagedEmailProfileRequired = true,
};

// To initialize your graphClient, see https://learn.microsoft.com/en-us/graph/sdks/create-client?from=snippets&tabs=csharp
var result = await graphClient.DeviceManagement.DeviceCompliancePolicies["{deviceCompliancePolicy-id}"].PatchAsync(requestBody);


```