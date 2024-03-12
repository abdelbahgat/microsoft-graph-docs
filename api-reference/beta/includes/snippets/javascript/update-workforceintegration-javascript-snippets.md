---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

const workforceIntegration = {
  displayName: 'displayName-value',
  apiVersion: 99,
  encryption: {
    protocol: 'protocol-value',
    secret: 'secret-value'
  },
  isActive: true,
  url: 'url-value',
  supports: 'supports-value'
};

await client.api('/teamwork/workforceIntegrations/{workforceIntegrationId}')
	.version('beta')
	.update(workforceIntegration);

```