---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

await client.api('/onPremisesPublishingProfiles/provisioning/publishedResources/1234b780-965f-4149-85c5-a8c73e58b67d/agentGroups/8832388F-3814-4952-B288-FFB62081FE25/$ref')
	.version('beta')
	.delete();

```