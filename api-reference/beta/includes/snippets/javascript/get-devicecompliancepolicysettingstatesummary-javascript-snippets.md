---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

let deviceCompliancePolicySettingStateSummary = await client.api('/tenantRelationships/managedTenants/deviceCompliancePolicySettingStateSummaries/{deviceCompliancePolicySettingStateSummaryId}')
	.version('beta')
	.get();

```