---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

var parameters = new List<SynchronizationJobApplicationParameters>()
{
	new SynchronizationJobApplicationParameters
	{
		RuleId = "33f7c90d-bf71-41b1-bda6-aaf0ddbee5d8#V2",
		Subjects = new List<SynchronizationJobSubject>()
		{
			new SynchronizationJobSubject
			{
				ObjectId = "8213fd99-d6b6-417b-8e13-af6334856215",
				ObjectTypeName = "Group",
				Links = new SynchronizationLinkedObjects
				{
					Members = new List<SynchronizationJobSubject>()
					{
						new SynchronizationJobSubject
						{
							ObjectId = "cbc86211-6ada-4803-b73f-8039cf56d8a2",
							ObjectTypeName = "User"
						},
						new SynchronizationJobSubject
						{
							ObjectId = "2bc86211-6ada-4803-b73f-8039cf56d8a2",
							ObjectTypeName = "User"
						}
					}
				}
			}
		}
	}
};

await graphClient.ServicePrincipals["{servicePrincipal-id}"].Synchronization.Jobs["{synchronizationJob-id}"]
	.ProvisionOnDemand(parameters)
	.Request()
	.PostAsync();

```