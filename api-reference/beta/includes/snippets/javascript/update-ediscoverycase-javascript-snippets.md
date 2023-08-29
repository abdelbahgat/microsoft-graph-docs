---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

const ediscoveryCase = {
    displayName: 'My Case 1 - Renamed',
    description: 'Updated description'
};

await client.api('/security/cases/eDiscoverycases/22aa2acd-7554-4330-9ba9-ce20014aaae4')
	.version('beta')
	.update(ediscoveryCase);

```