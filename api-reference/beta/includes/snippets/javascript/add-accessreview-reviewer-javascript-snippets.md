---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

const accessReviewReviewer = {
    id: '006111db-0810-4494-a6df-904d368bd81b'
};

await client.api('/accessReviews/2b83cc42-09db-46f6-8c6e-16fec466a82d/reviewers')
	.version('beta')
	.post(accessReviewReviewer);

```