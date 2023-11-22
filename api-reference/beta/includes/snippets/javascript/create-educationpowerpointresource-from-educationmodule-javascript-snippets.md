---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

const educationModuleResource = {
    resource: {
        '@odata.type': '#microsoft.graph.educationPowerPointResource',
        displayName: 'ppt_test.pptx',
        fileUrl: 'https://graph.microsoft.com/v1.0/drives/b!-Ik2sRPLDEWy_bR8l75jfeDcpXQcRKVOmcml10NQLQ1F2UVvTgEnTKi0GO59dbCL/items/01VANVJQZEG2AM23OQ5NA2LFTHERBABBK6'
    }
};

await client.api('/education/classes/37d99af7-cfc5-4e3b-8566-f7d40e4a2070/modules/74b318fa-e882-4dad-8e1c-dab091b12fe7/resources')
	.version('beta')
	.post(educationModuleResource);

```