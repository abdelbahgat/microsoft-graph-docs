---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

const tenantCustomizedInformation = {
  '@odata.type': '#microsoft.graph.managedTenants.tenantCustomizedInformation',
  tenantId: 'String',
  contacts: [
    {
      '@odata.type': 'microsoft.graph.managedTenants.tenantContactInformation',
      name: 'String',
      title: 'String',
      email: 'String',
      phone: 'String',
      notes: 'String'
    }
  ],
  website: 'String'
};

await client.api('/tenantRelationships/managedTenants/tenantsCustomizedInformation/{tenantCustomizedInformationId}')
	.version('beta')
	.update(tenantCustomizedInformation);

```