---
description: "Automatically generated file. DO NOT MODIFY"
---

```java

GraphServiceClient graphClient = GraphServiceClient.builder().authenticationProvider( authProvider ).buildClient();

ConversationThread conversationThread = new ConversationThread();
conversationThread.topic = "Take your wellness days and rest";
LinkedList<Post> postsList = new LinkedList<Post>();
Post posts = new Post();
ItemBody body = new ItemBody();
body.contentType = BodyType.HTML;
body.content = "Waiting for the summer holidays.";
posts.body = body;
postsList.add(posts);
PostCollectionResponse postCollectionResponse = new PostCollectionResponse();
postCollectionResponse.value = postsList;
PostCollectionPage postCollectionPage = new PostCollectionPage(postCollectionResponse, null);
conversationThread.posts = postCollectionPage;

graphClient.groups("{id}").conversations("{id}").threads()
	.buildRequest()
	.post(conversationThread);

```