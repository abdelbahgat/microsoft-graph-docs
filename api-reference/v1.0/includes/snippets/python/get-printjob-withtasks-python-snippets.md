---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(credentials, scopes)

query_params = PrintJobItemRequestBuilder.PrintJobItemRequestBuilderGetQueryParameters(
		expand = ["tasks"],
)

request_configuration = PrintJobItemRequestBuilder.PrintJobItemRequestBuilderGetRequestConfiguration(
query_parameters = query_params,
)

result = await graph_client.print.printers.by_printer_id('printer-id').jobs.by_print_job_id('printJob-id').get(request_configuration = request_configuration)


```