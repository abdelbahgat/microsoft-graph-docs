---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

const vppToken = {
  '@odata.type': '#microsoft.graph.vppToken',
  organizationName: 'Organization Name value',
  vppTokenAccountType: 'education',
  appleId: 'Apple Id value',
  expirationDateTime: '2016-12-31T23:57:57.2481234-08:00',
  lastSyncDateTime: '2017-01-01T00:02:49.3205976-08:00',
  token: 'Token value',
  state: 'valid',
  lastSyncStatus: 'inProgress',
  automaticallyUpdateApps: true,
  countryOrRegion: 'Country Or Region value'
};

await client.api('/deviceAppManagement/vppTokens')
	.post(vppToken);

```