---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

let childHostPairs = await client.api('/security/threatIntelligence/hosts/contoso.com/childHostPairs')
	.version('beta')
	.get();

```