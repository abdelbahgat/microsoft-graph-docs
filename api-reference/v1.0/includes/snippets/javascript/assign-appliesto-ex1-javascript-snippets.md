---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

const appManagementPolicy = {
 '@odata.id':'https://graph.microsoft.com/v1.0/policies/appManagementPolicies/{id}'
};

await client.api('/applications/{id}/appManagementPolicies/$ref')
	.post(appManagementPolicy);

```