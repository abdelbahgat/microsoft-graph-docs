---
description: "Automatically generated file. DO NOT MODIFY"
---

```objc

MSHTTPClient *httpClient = [MSClientFactory createHTTPClientWithAuthenticationProvider:authenticationProvider];

NSString *MSGraphBaseURL = @"https://graph.microsoft.com/beta/";
NSMutableURLRequest *urlRequest = [NSMutableURLRequest requestWithURL:[NSURL URLWithString:[MSGraphBaseURL stringByAppendingString:@"/me/messages/AAMkADA1MTAAAH5JaLAAA=/createForward"]]];
[urlRequest setHTTPMethod:@"POST"];
[urlRequest setValue:@"application/json" forHTTPHeaderField:@"Content-Type"];

NSMutableDictionary *payloadDictionary = [[NSMutableDictionary alloc] init];

MSGraphMessage *message = [[MSGraphMessage alloc] init];
[message setIsDeliveryReceiptRequested: true];
NSMutableArray *toRecipientsList = [[NSMutableArray alloc] init];
MSGraphRecipient *toRecipients = [[MSGraphRecipient alloc] init];
MSGraphEmailAddress *emailAddress = [[MSGraphEmailAddress alloc] init];
[emailAddress setAddress:@"danas@contoso.onmicrosoft.com"];
[emailAddress setName:@"Dana Swope"];
[toRecipients setEmailAddress:emailAddress];
[toRecipientsList addObject: toRecipients];
[message setToRecipients:toRecipientsList];
payloadDictionary[@"message"] = message;

NSString *comment = @"Dana, just want to make sure you get this; you'll need this if the project gets approved.";
payloadDictionary[@"comment"] = comment;

NSData *data = [NSJSONSerialization dataWithJSONObject:payloadDictionary options:kNilOptions error:&error];
[urlRequest setHTTPBody:data];

MSURLSessionDataTask *meDataTask = [httpClient dataTaskWithRequest:urlRequest 
	completionHandler: ^(NSData *data, NSURLResponse *response, NSError *nserror) {

		//Request Completed

}];

[meDataTask execute];

```