---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

var graphClient = new GraphServiceClient(requestAdapter);

var requestBody = new Microsoft.Graph.Beta.ServicePrincipals.Item.CreatePasswordSingleSignOnCredentials.CreatePasswordSingleSignOnCredentialsPostRequestBody
{
	Id = "5793aa3b-cca9-4794-679a240f8b58",
	Credentials = new List<Credential>
	{
		new Credential
		{
			FieldId = "param_username",
			Value = "myusername",
			Type = "username",
		},
		new Credential
		{
			FieldId = "param_password",
			Value = "pa$$w0rd",
			Type = "password",
		},
	},
};
var result = await graphClient.ServicePrincipals["{servicePrincipal-id}"].CreatePasswordSingleSignOnCredentials.PostAsync(requestBody);


```