---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

const authenticationMethodConfiguration = {
  '@odata.type': '#microsoft.graph.voiceAuthenticationMethodConfiguration',
  isOfficePhoneAllowed: 'false'
};

await client.api('/policies/authenticationMethodsPolicy/authenticationMethodConfigurations/voice')
	.version('beta')
	.update(authenticationMethodConfiguration);

```