---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

const personInterest = {
  categories: [
    'Sports'
  ]
};

await client.api('/me/profile/interests/{id}')
	.version('beta')
	.update(personInterest);

```