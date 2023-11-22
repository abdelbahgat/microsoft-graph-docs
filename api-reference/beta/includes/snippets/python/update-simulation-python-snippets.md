---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(credentials, scopes)

request_body = Simulation(
	display_name = "Graph Simulation",
	duration_in_days = 7,
	attack_technique = SimulationAttackTechnique.CredentialHarvesting,
	attack_type = SimulationAttackType.Social,
	status = SimulationStatus.Scheduled,
	included_account_target = AddressBookAccountTargetContent(
		odata_type = "#microsoft.graph.addressBookAccountTargetContent",
		type = AccountTargetContentType.AddressBook,
		account_target_emails = [
			"faiza@contoso.com",
		],
	),
	excluded_account_target = AddressBookAccountTargetContent(
		odata_type = "#microsoft.graph.addressBookAccountTargetContent",
		type = AccountTargetContentType.AddressBook,
		account_target_emails = [
			"sam@contoso.com",
		],
	),
	additional_data = {
			"@odata_etag" : "\"0100aa9b-0000-0100-0000-6396fa270000\"",
			"payload@odata_bind" : "https://graph.microsoft.com/beta/security/attacksimulation/payloads/12345678-9abc-def0-123456789a",
	}
)

result = await graph_client.security.attack_simulation.simulations.by_simulation_id('simulation-id').patch(request_body)


```