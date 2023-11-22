---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

const profileCardProperty = {
  annotations: [
    {
      displayName: 'Cost Center',
      localizations: [
        {
          languageTag: 'nb-NO',
          displayName: 'Kostnadssenter'
        }
      ]
    }
  ]
};

await client.api('/admin/people/profileCardProperties/CustomAttribute1')
	.version('beta')
	.update(profileCardProperty);

```