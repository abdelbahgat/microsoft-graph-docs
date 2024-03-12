---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

const addKey = {
    keyCredential: {
        type: 'X509CertAndPassword',
        usage: 'Sign',
        key: 'MIIDYDCCAki...'
    },
    passwordCredential: {
        secretText: 'MKTr0w1...'
    },
    proof: 'eyJ0eXAiOiJ...'
};

await client.api('/servicePrincipals/{id}/addKey')
	.version('beta')
	.post(addKey);

```