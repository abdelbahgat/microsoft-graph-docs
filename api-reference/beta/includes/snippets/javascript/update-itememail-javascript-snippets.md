---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

const itemEmail = {
  displayName: 'Business Email',
  type: 'work'
};

await client.api('/users/{userId}/profile/emails/{id}')
	.version('beta')
	.update(itemEmail);

```