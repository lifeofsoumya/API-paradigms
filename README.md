## TRPC Sample Code
```javascript
Copy code
// Define a TRPC endpoint
const trpc = require('@trpc/server');
const app = trpc.createRouter();

app.query('hello', {
  resolve() {
    return 'world';
  },
});

// Start the TRPC server
const http = require('http');
const server = http.createServer(app.handler);

server.listen(3000, () => {
  console.log('TRPC server running on port 3000');
});
```





## GraphQL Sample Code
```javascript
Copy code
// Define a GraphQL schema
const { GraphQLSchema, GraphQLObjectType, GraphQLString } = require('graphql');

const schema = new GraphQLSchema({
  query: new GraphQLObjectType({
    name: 'HelloWorld',
    fields: {
      hello: {
        type: GraphQLString,
        resolve() {
          return 'world';
        },
      },
    },
  }),
});

// Start the GraphQL server
const express = require('express');
const { graphqlHTTP } = require('express-graphql');

const app = express();

app.use('/graphql', graphqlHTTP({
  schema: schema,
  graphiql: true,
}));

app.listen(3000, () => {
  console.log('GraphQL server running on port 3000');
});
```

## REST Sample Code
```javascript
Copy code
// Define a REST endpoint
const express = require('express');
const app = express();

app.get('/hello', (req, res) => {
  res.send('world');
});

// Start the REST server
app.listen(3000, () => {
  console.log('REST server running on port 3000');
});
```