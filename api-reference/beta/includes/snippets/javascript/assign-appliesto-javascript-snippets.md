---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

const appManagementPolicy = {
 '@odata.id':'https://graph.microsoft.com/beta/policies/appManagementPolicies/{id}'
};

await client.api('/servicePrincipals/{id}/appManagementPolicies/$ref')
	.version('beta')
	.post(appManagementPolicy);

```