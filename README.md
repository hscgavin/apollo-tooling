# Apollo client code generator

This is an early prototype of a tool to generate client code based on a GraphQL schema and query documents.

It currently only generates Swift code, and only for a subset of GraphQL queries. Most importantly, fragments are not yet supported. See [Apollo iOS client](https://github.com/apollostack/apollo-ios) for a more detailed description of the proposed mapping to Swift, as well as runtime support for performing queries.

For example, given the schema and query documents in [this directory](https://github.com/apollostack/apollo-codegen/tree/master/test/starwars), `apollo-codegen` will generate [these Swift files](https://github.com/apollostack/apollo-codegen/tree/master/test/swift/expectedOutput).

## Usage

If you want to experiment with the tool, you can install the `apollo-codegen` command globally:

```sh
npm install apollo-codegen -g
```

To download a GraphQL schema by sending an introspection query to a server:

```sh
apollo-codegen download-schema http://localhost:3000/graphql --output GitHuntAPI/Definitions/schema.json
```

To generate Swift code from a set of query definitions in `.graphql` files:

```sh
apollo-codegen generate GitHuntAPI/Definitions/**/*.graphql --schema GitHuntAPI/Definitions/schema.json --output GitHuntAPI/Generated
```