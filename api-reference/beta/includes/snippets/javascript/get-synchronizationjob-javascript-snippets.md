---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

let synchronizationJob = await client.api('/servicePrincipals/{id}/synchronization/jobs/{jobId}/')
	.version('beta')
	.get();

```