---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

const unmuteParticipantOperation = {
  clientContext: 'clientContext-value'
};

await client.api('/communications/calls/57dab8b1-894c-409a-b240-bd8beae78896/unmute')
	.version('beta')
	.post(unmuteParticipantOperation);

```