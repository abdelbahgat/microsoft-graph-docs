---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

const cloudPcCrossCloudGovernmentOrganizationMapping = {};

await client.api('/deviceManagement/virtualEndpoint/crossCloudGovernmentOrganizationMapping')
	.version('beta')
	.post(cloudPcCrossCloudGovernmentOrganizationMapping);

```