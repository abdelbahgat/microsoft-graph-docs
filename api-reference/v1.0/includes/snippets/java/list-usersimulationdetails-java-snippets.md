---
description: "Automatically generated file. DO NOT MODIFY"
---

```java

GraphServiceClient graphClient = GraphServiceClient.builder().authenticationProvider( authProvider ).buildClient();

UserSimulationDetailsCollectionPage simulationUsers = graphClient.customRequest("/security/attackSimulation/simulations/f1b13829-3829-f1b1-2938-b1f12938b1a/report/simulationUsers", UserSimulationDetailsCollectionPage.class)
	.buildRequest()
	.get();

```