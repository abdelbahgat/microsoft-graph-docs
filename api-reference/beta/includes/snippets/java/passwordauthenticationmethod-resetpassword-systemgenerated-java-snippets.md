---
description: "Automatically generated file. DO NOT MODIFY"
---

```java

GraphServiceClient graphClient = GraphServiceClient.builder().authenticationProvider( authProvider ).buildClient();

graphClient.users("6ea91a8d-e32e-41a1-b7bd-d2d185eed0e0").authentication().passwordMethods("28c10230-6103-485e-b985-444c60001490")
	.resetPassword(AuthenticationMethodResetPasswordParameterSet
		.newBuilder()
		.withNewPassword(null)
		.withRequireChangeOnNextSignIn(null)
		.build())
	.buildRequest()
	.post();

```