---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

let devices = await client.api('/devices')
	.header('ConsistencyLevel','eventual')
	.filter('extensionAttributes/extensionAttribute1 eq \'BYOD-Device\'')
	.get();

```