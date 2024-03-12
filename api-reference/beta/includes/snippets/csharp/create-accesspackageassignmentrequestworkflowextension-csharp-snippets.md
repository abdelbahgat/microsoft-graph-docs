---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

var graphClient = new GraphServiceClient(requestAdapter);

var requestBody = new CustomCalloutExtension
{
	AdditionalData = new Dictionary<string, object>
	{
		{
			"value" , new 
			{
				OdataType = "#microsoft.graph.accessPackageAssignmentRequestWorkflowExtension",
				DisplayName = "test_action_0124_email",
				Description = "this is for graph testing only",
				EndpointConfiguration = new 
				{
					OdataType = "#microsoft.graph.logicAppTriggerEndpointConfiguration",
					SubscriptionId = "38ab2ccc-3747-4567-b36b-9478f5602f0d",
					ResourceGroupName = "test",
					LogicAppWorkflowName = "elm-extension-email",
				},
				AuthenticationConfiguration = new 
				{
					OdataType = "#microsoft.graph.azureAdPopTokenAuthentication",
				},
				CallbackConfiguration = new 
				{
					OdataType = "microsoft.graph.customExtensionCallbackConfiguration",
					DurationBeforeTimeout = "PT1H",
				},
			}
		},
	},
};
var result = await graphClient.IdentityGovernance.EntitlementManagement.AccessPackageCatalogs["{accessPackageCatalog-id}"].AccessPackageCustomWorkflowExtensions.PostAsync(requestBody);


```