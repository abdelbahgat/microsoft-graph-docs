---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

const term = {
  labels: [
    {
      languageTag: 'en-US',
      name: 'Car',
      isDefault: true
    }
  ]
};

await client.api('/termStore/sets/{setId}/children')
	.version('beta')
	.post(term);

```