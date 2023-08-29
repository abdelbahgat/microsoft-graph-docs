---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

const ediscoveryReviewSetQuery = {
    displayName: 'My Query 1 (update)',
    contentQuery: '(Author=\"edisons\")'
};

await client.api('/security/cases/ediscoverycases/58399dff-cebe-478f-b1af-d3227f1fd645/reviewSets/63ef0fd7-0db2-45eb-a9d7-7d75c8239873/queries/5f426fdc-f027-40db-b7cc-453cf06dc996')
	.update(ediscoveryReviewSetQuery);

```