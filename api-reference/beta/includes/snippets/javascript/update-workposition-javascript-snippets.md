---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

const workPosition = {
  isCurrent: true
};

await client.api('/me/profile/positions/{id}')
	.version('beta')
	.update(workPosition);

```