---
description: "Automatically generated file. DO NOT MODIFY"
---

```java

GraphServiceClient graphClient = GraphServiceClient.builder().authenticationProvider( authProvider ).buildClient();

Contact contact = new Contact();
contact.parentFolderId = "parentFolderId-value";
contact.birthday = OffsetDateTimeSerializer.deserialize("2016-10-19T10:37:00Z");
contact.fileAs = "fileAs-value";
contact.displayName = "displayName-value";
contact.givenName = "givenName-value";
contact.initials = "initials-value";

graphClient.me().contactFolders("{id}").contacts()
	.buildRequest()
	.post(contact);

```