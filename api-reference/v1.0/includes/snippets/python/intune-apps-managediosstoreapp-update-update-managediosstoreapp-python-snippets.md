---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(credentials, scopes)

request_body = ManagedIOSStoreApp(
	odata_type = "#microsoft.graph.managedIOSStoreApp",
	display_name = "Display Name value",
	description = "Description value",
	publisher = "Publisher value",
	large_icon = MimeContent(
		odata_type = "microsoft.graph.mimeContent",
		type = "Type value",
		value = base64.urlsafe_b64decode("dmFsdWU="),
	),
	is_featured = True,
	privacy_information_url = "https://example.com/privacyInformationUrl/",
	information_url = "https://example.com/informationUrl/",
	owner = "Owner value",
	developer = "Developer value",
	notes = "Notes value",
	publishing_state = MobileAppPublishingState.Processing,
	app_availability = ManagedAppAvailability.LineOfBusiness,
	version = "Version value",
	bundle_id = "Bundle Id value",
	app_store_url = "https://example.com/appStoreUrl/",
	applicable_device_type = IosDeviceType(
		odata_type = "microsoft.graph.iosDeviceType",
		i_pad = True,
		i_phone_and_i_pod = True,
	),
	minimum_supported_operating_system = IosMinimumOperatingSystem(
		odata_type = "microsoft.graph.iosMinimumOperatingSystem",
		v8_0 = True,
		v9_0 = True,
		v10_0 = True,
		v11_0 = True,
		v12_0 = True,
		v13_0 = True,
		v14_0 = True,
		v15_0 = True,
	),
)

result = await graph_client.device_app_management.mobile_apps.by_mobile_app_id('mobileApp-id').patch(request_body)


```