<!-- markdownlint-disable MD041 -->

```typescript
// GET https://graph.microsoft.com/v1.0/me?$select=displayName,jobTitle

let user = await client.api('/me')
  .select('displayName', 'jobTitle')
  .get();
```
