---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

let decisions = await client.api('/identityGovernance/accessReviews/definitions/16d424f6-0100-4bf1-9ebc-fe009c5e5006/instances/bb14c722-51b8-4962-9bd2-1d96ba773d80/stages/8f0a8999-205b-4c29-a68c-2bee353fd4c5/decisions')
	.version('beta')
	.get();

```