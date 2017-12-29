# permissions

## Get started

### Deploy the Graphcool database service

You can now [deploy](https://graph.cool/docs/reference/graphcool-cli/commands-aiteerae6l#graphcool-deploy) the Graphcool service that's defined in the `database` directory:

```sh
cd database
graphcool deploy
```

> Note: Whenever you make changes to files in the `database` directory, you need to invoke `graphcool deploy` again to make sure your changes get applied to the running service.

### 3. Deploy the GraphQL server

Your GraphQL web server that's powered by [`graphql-yoga`](https://github.com/graphcool/graphql-yoga/) is now ready to be deployed. This is because the Graphcool database service it connects to is now available.

```sh
cd ..
yarn start
```

The server is now running on [http://localhost:4000](http://localhost:4000).

## Testing the service

The easiest way to test the deployed service is by using a [GraphQL Playground](https://github.com/graphcool/graphql-playground).

### Open a Playground

You can open a Playground by navigating to [http://localhost:4000](http://localhost:4000) in your browser or with the following command:

```sh
graphcool playground
```

### Register a new user with the `signup` mutation

You can send the following mutation in the Playground to create a new `User` node and at the same time retrieve an authentication token for it:

```graphql
mutation {
  signup(email: "alice@graph.cool" password: "graphql") {
    token
    user {
      id
    }
  }
}
```
