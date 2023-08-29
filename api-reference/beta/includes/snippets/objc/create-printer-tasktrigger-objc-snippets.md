---
description: "Automatically generated file. DO NOT MODIFY"
---

```objc

MSHTTPClient *httpClient = [MSClientFactory createHTTPClientWithAuthenticationProvider:authenticationProvider];

NSString *MSGraphBaseURL = @"https://graph.microsoft.com/beta/";
NSMutableURLRequest *urlRequest = [NSMutableURLRequest requestWithURL:[NSURL URLWithString:[MSGraphBaseURL stringByAppendingString:@"/print/printers/ae63f617-4856-4b45-8ea9-69dfbeea230e/taskTriggers"]]];
[urlRequest setHTTPMethod:@"POST"];

MSGraphPrintTaskTrigger *printTaskTrigger = [[MSGraphPrintTaskTrigger alloc] init];
[printTaskTrigger setEvent: [MSGraphPrintEvent jobStarted]];

NSError *error;
NSData *printTaskTriggerData = [printTaskTrigger getSerializedDataWithError:&error];
[urlRequest setHTTPBody:printTaskTriggerData];

MSURLSessionDataTask *meDataTask = [httpClient dataTaskWithRequest:urlRequest 
	completionHandler: ^(NSData *data, NSURLResponse *response, NSError *nserror) {

		//Request Completed

}];

[meDataTask execute];

```