# WunderGraph subscriptions example - SSE

### Protocol

https://github.com/enisdenjo/graphql-sse/blob/master/PROTOCOL.md

### Configuration

```typescript
const schema = `
schema {
  query: Query
  subscription: Subscription
}

type Query {
  hello: String
}

type Subscription {
  greetings: String
}
`;

const greetings = introspect.graphql({
  apiNamespace: 'sse',
  url: 'http://127.0.0.1:4000/graphql/stream',
  loadSchemaFromString: schema,
  subscriptionsUseSSE: true,
});
```

#### Getting started

```shell
npm install && npm start
```

#### Check results

```shell
curl -N http://localhost:9991/app/main/operations/Sse
```

#### SSE output

```shell
 curl -N http://localhost:9991/app/main/operations/Sse\?wg_sse\=true
```

#### Call your custom GraphQL server

```shell
curl -X GET http://localhost:9991/app/main/operations/Hello
```

## Learn More

Read the [Docs](https://wundergraph.com/docs).

## Got Questions?

Join us on [Discord](https://wundergraph.com/discord)!
