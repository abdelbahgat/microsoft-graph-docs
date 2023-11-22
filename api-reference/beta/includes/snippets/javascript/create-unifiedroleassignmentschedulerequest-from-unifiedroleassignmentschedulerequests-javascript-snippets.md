---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

const unifiedRoleAssignmentScheduleRequest = {
  action: 'AdminAssign',
  justification: 'Assign User Admin to IT Helpdesk (User) group',
  roleDefinitionId: 'fdd7a751-b60b-444a-984c-02652fe8fa1c',
  directoryScopeId: '/',
  principalId: '07706ff1-46c7-4847-ae33-3003830675a1',
  scheduleInfo: {
    startDateTime: '2021-07-01T00:00:00Z',
    expiration: {
      type: 'NoExpiration'
    }
  }
};

await client.api('/roleManagement/directory/roleAssignmentScheduleRequests/')
	.version('beta')
	.post(unifiedRoleAssignmentScheduleRequest);

```