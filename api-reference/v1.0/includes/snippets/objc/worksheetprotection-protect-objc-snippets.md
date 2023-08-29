---
description: "Automatically generated file. DO NOT MODIFY"
---

```objc

MSHTTPClient *httpClient = [MSClientFactory createHTTPClientWithAuthenticationProvider:authenticationProvider];

NSString *MSGraphBaseURL = @"https://graph.microsoft.com/v1.0/";
NSMutableURLRequest *urlRequest = [NSMutableURLRequest requestWithURL:[NSURL URLWithString:[MSGraphBaseURL stringByAppendingString:@"/me/drive/items/{id}/workbook/worksheets/{id|name}/protection/protect"]]];
[urlRequest setHTTPMethod:@"POST"];
[urlRequest setValue:@"application/json" forHTTPHeaderField:@"Content-Type"];

NSMutableDictionary *payloadDictionary = [[NSMutableDictionary alloc] init];

MSGraphWorkbookWorksheetProtectionOptions *options = [[MSGraphWorkbookWorksheetProtectionOptions alloc] init];
[options setAllowFormatCells: true];
[options setAllowFormatColumns: true];
[options setAllowFormatRows: true];
[options setAllowInsertColumns: true];
[options setAllowInsertRows: true];
[options setAllowInsertHyperlinks: true];
[options setAllowDeleteColumns: true];
[options setAllowDeleteRows: true];
[options setAllowSort: true];
[options setAllowAutoFilter: true];
[options setAllowPivotTables: true];
payloadDictionary[@"options"] = options;

NSData *data = [NSJSONSerialization dataWithJSONObject:payloadDictionary options:kNilOptions error:&error];
[urlRequest setHTTPBody:data];

MSURLSessionDataTask *meDataTask = [httpClient dataTaskWithRequest:urlRequest 
	completionHandler: ^(NSData *data, NSURLResponse *response, NSError *nserror) {

		//Request Completed

}];

[meDataTask execute];

```