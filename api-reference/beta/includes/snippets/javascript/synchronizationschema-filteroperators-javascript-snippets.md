---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

let filterOperators = await client.api('/servicePrincipals/{id}/synchronization/jobs/{jobId}/schema/filterOperators')
	.version('beta')
	.get();

```