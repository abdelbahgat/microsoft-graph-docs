---
description: "Automatically generated file. DO NOT MODIFY"
---

```objc

MSHTTPClient *httpClient = [MSClientFactory createHTTPClientWithAuthenticationProvider:authenticationProvider];

NSString *MSGraphBaseURL = @"https://graph.microsoft.com/beta/";
NSMutableURLRequest *urlRequest = [NSMutableURLRequest requestWithURL:[NSURL URLWithString:[MSGraphBaseURL stringByAppendingString:@"/groups/1848753d-185d-4c08-a4e4-6ee40521d115/threads/AAQkADJUdfolA==/reply"]]];
[urlRequest setHTTPMethod:@"POST"];
[urlRequest setValue:@"application/json" forHTTPHeaderField:@"Content-Type"];

NSMutableDictionary *payloadDictionary = [[NSMutableDictionary alloc] init];

MSGraphPost *post = [[MSGraphPost alloc] init];
MSGraphItemBody *body = [[MSGraphItemBody alloc] init];
[body setContentType: [MSGraphBodyType text]];
[body setContent:@"Which quarter does that file cover? See my attachment."];
[post setBody:body];
NSMutableArray *attachmentsList = [[NSMutableArray alloc] init];
MSGraphAttachment *attachments = [[MSGraphAttachment alloc] init];
[attachments setName:@"Another file as attachment"];
[attachments setContentBytes:@"VGhpcyBpcyBhIGZpbGUgdG8gYmUgYXR0YWNoZWQu"];
[attachmentsList addObject: attachments];
[post setAttachments:attachmentsList];
payloadDictionary[@"post"] = post;

NSData *data = [NSJSONSerialization dataWithJSONObject:payloadDictionary options:kNilOptions error:&error];
[urlRequest setHTTPBody:data];

MSURLSessionDataTask *meDataTask = [httpClient dataTaskWithRequest:urlRequest 
	completionHandler: ^(NSData *data, NSURLResponse *response, NSError *nserror) {

		//Request Completed

}];

[meDataTask execute];

```