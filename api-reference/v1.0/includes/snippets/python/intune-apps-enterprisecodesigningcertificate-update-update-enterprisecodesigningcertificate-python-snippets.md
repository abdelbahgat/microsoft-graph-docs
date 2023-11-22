---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(credentials, scopes)

request_body = EnterpriseCodeSigningCertificate(
	odata_type = "#microsoft.graph.enterpriseCodeSigningCertificate",
	content = base64.urlsafe_b64decode("Y29udGVudA=="),
	status = CertificateStatus.Provisioned,
	subject_name = "Subject Name value",
	subject = "Subject value",
	issuer_name = "Issuer Name value",
	issuer = "Issuer value",
	expiration_date_time = "2016-12-31T23:57:57.2481234-08:00",
	upload_date_time = "2016-12-31T23:58:46.5747426-08:00",
)

result = await graph_client.device_app_management.enterprise_code_signing_certificates.by_enterprise_code_signing_certificate_id('enterpriseCodeSigningCertificate-id').patch(request_body)


```