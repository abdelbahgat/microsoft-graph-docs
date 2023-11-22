---
description: "Automatically generated file. DO NOT MODIFY"
---

```java

GraphServiceClient graphClient = GraphServiceClient.builder().authenticationProvider( authProvider ).buildClient();

Device device = new Device();
device.accountEnabled = true;
LinkedList<AlternativeSecurityId> alternativeSecurityIdsList = new LinkedList<AlternativeSecurityId>();
AlternativeSecurityId alternativeSecurityIds = new AlternativeSecurityId();
alternativeSecurityIds.type = 99;
alternativeSecurityIds.identityProvider = "identityProvider-value";
alternativeSecurityIds.key = Base64.getDecoder().decode("base64Y3YxN2E1MWFlYw==");
alternativeSecurityIdsList.add(alternativeSecurityIds);
device.alternativeSecurityIds = alternativeSecurityIdsList;
device.approximateLastSignInDateTime = OffsetDateTimeSerializer.deserialize("2016-10-19T10:37:00Z");
device.deviceId = "deviceId-value";
device.deviceMetadata = "deviceMetadata-value";
device.deviceVersion = 99;

graphClient.devices()
	.buildRequest()
	.post(device);

```