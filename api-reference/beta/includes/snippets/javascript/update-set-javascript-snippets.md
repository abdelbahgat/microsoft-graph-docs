---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

const set = {
  description: 'mySet'
};

await client.api('/termStore/sets/{setId}')
	.version('beta')
	.update(set);

```