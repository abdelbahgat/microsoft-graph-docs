---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(credentials, scopes)

request_body = TeamsTab(
	display_name = "My Contoso Tab",
	configuration = TeamsTabConfiguration(
		entity_id = "2DCA2E6C7A10415CAF6B8AB6661B3154",
		content_url = "https://www.contoso.com/Orders/2DCA2E6C7A10415CAF6B8AB6661B3154/tabView",
		website_url = "https://www.contoso.com/Orders/2DCA2E6C7A10415CAF6B8AB6661B3154",
		remove_url = "https://www.contoso.com/Orders/2DCA2E6C7A10415CAF6B8AB6661B3154/uninstallTab",
	),
	additional_data = {
			"teams_app@odata_bind" : "https://graph.microsoft.com/v1.0/appCatalogs/teamsApps/06805b9e-77e3-4b93-ac81-525eb87513b8",
	}
)

result = await graph_client.teams.by_team_id('team-id').channels.by_channel_id('channel-id').tabs.post(request_body)


```