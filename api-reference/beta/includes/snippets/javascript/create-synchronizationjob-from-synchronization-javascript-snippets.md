---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

const synchronizationJob = {
    templateId: 'BoxOutDelta'
};

await client.api('/servicePrincipals/{id}/synchronization/jobs')
	.version('beta')
	.post(synchronizationJob);

```