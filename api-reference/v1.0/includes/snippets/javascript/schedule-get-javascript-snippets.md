---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

let schedule = await client.api('/teams/{teamId}/schedule')
	.get();

```