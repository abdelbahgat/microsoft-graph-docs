---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

const application = {
    authenticationBehaviors: {
        removeUnverifiedEmailClaim: null
    }
};

await client.api('/applications/03ef14b0-ca33-4840-8f4f-d6e91916010e/')
	.version('beta')
	.update(application);

```