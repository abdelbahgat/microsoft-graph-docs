---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

var deviceCompliancePolicySettingStateSummary = await graphClient.TenantRelationships.ManagedTenants.DeviceCompliancePolicySettingStateSummaries["{managedTenants.deviceCompliancePolicySettingStateSummary-id}"]
	.Request()
	.GetAsync();

```