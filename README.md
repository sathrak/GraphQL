
# What is GraphQL?
  GraphQL is a query language created by Facebook in 2012 which provides a common interface between the client and the server for data fetching and manipulations.

  The client asks for various data from the GraphQL server via queries. The response format is described in the query and defined by the client instead of the server: they are called client‐specified queries.
  The structure of the data is not hardcoded as in traditional REST APIs - this makes retrieving data from the server more efficient for the client.

  For example, the client can ask for linked resources without defining new API endpoints. With the following GraphQL query, we can ask for the user specific fields and the linked friends resource as well.
```HTML
  {
  user(id: 1) {
    name
    age
    friends {
      name
    }
  }
}  
```
In a resource based REST API it would look something like:

```HTML
GET /users/1 and GET /users/1/friends
```

## GraphQL overview
  It's important to mention that GraphQL is not language specific, it's just a specification between the client and the server. Any client should be able to communicate with any server if they speak the common language: GraphQL.
  
### Key concepts of the GraphQL query language are:
    - Hierarchical
    - Product‐centric
    - Strong‐typing
    - Client‐specified queries
    - Introspective
  I would like to highlight strong-typing here which means that GraphQL introduces an application level type system. It's a contract between the client and server which means that your server in the background may use different internal types. The only thing here what matters is that the GraphQL server must be able to receive GraphQL queries, decide if that it is syntactically correct and provide the described data for that.
  
# Advantages of GraphQL:

### GraphQL is declarative: 
   Query responses are decided by the client rather than the server. A GraphQL query returns exactly what a client asks for and no more.

### GraphQL is compositional: 
   A GraphQL query itself is a hierarchical set of fields. The query is shaped just like the data it returns. It is a natural way for product engineers to describe data requirements.

### GraphQL is strongly-typed: 
  A GraphQL query can be ensured to be valid within a GraphQL type system at development time allowing the server to make guarantees about the response. This makes it easier to build high-quality client tools
  
  
