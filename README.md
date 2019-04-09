
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
  
  
#What is GraphQL ?#

GraphQL is an open source server-side technology which was developed by Facebook to optimize RESTful API calls. 
It is an execution engine and a data query language. 


    Implement GraphQL API using GraphQL

    Test GraphQL API using GraphiQL

    Build jQuery client applications to consume the API


##Why GraphQL##

	RESTful APIs follow clear and well-structured resource-oriented approach. 
	Sometimes it is not possible to fetch data with a single request. 
	This is where GraphQL comes handy. GraphQL structures data in the form of a graph with its powerful query syntax for traversing, retrieving, and modifying data.

###The following are advantages of using GraphQL query Language −###

	1. Ask for what you want − and get it
		Send a GraphQL query to your API and get exactly what you need. 
		GraphQL queries always return predictable results. Applications using GraphQL are fast and stable.

	The following example will help you understand this better −

		Let us consider a business object Student with the attributes id, firstName, lastName and collegeName.
		Suppose a mobile application needs to fetch only the firstName and id.
		If we design a REST endpoint like /api/v1/students, it will end up fetching data for all the fields for a student object. 

		"This problem can be solved by using GraphQL."

		Consider the GraphQL query given below −
		{
		   students {
			  id
			  firstName
		   }
		}

		This will return values only for the id and firstname fields. 

		{
		   "data": {
			  "students": [
				 {
				    "id": "S1001",
				    "firstName": "Mohtashim"
				 },
				 {
				    "id": "S1002",
				    "firstName": "Kannan"
				 }
			  ]
		   }
		}

	2. Get many resources in a single request

		GraphQL APIs fetch all the data your application need in a single request. 
		Applications using GraphQL can be quick even on slow mobile network connections.
		
	Let us consider one more business object, College which has the attributes: name and location.
	The Student business object has an association relationship with the College object. 
	If we were to use a REST API in order to fetch the details of students and their college, we will end up making two requests to the server like /api/v1/students and /api/v1/colleges. This will lead to under fetching of data with each request.So mobile applications are forced to make multiple calls to the server to get the desired data.

	
	"Mobile application can fetch details for both Student and College objects in a single request by using GraphQL."

	The following is a GraphQL query to fetch data −
	{
	   students{
		  id
		  firstName
		  lastName
		  college{
		     name
		     location
		  }
	   }
	}

	The output of the above query contains exactly those fields we have requested for as shown below −

	{
	   "data": {
		  "students": [
		     {
		        "id": "S1001",
		        "firstName": "Mohtashim",
		        "lastName": "Mohammad",
		        "college": {
		           "name": "CUSAT",
		           "location": "Kerala"
		        }
		     },
		     
		     {
		        "id": "S1002",
		        "firstName": "Kannan",
		        "lastName": "Sudhakaran",
		        "college": {
		           "name": "AMU",
		           "location": "Uttar Pradesh"
		        }
		     },
		     
		     {
		        "id": "S1003",
		        "firstName": "Kiran",
		        "lastName": "Panigrahi",
		        "college": {
		           "name": "AMU",
		           "location": "Uttar Pradesh"
		        }
		     }
		  ]
	   }
	}


	3. Describe what’s possible with a type system
		GraphQL is strongly typed and the queries are based on fields and their associated data types. 
		If there is type mismatch in a GraphQL query, server applications return clear and helpful error messages.

	An example of the Student and College data types is given below −
		type Query {
		   students:[Student]
		}

		type Student {
		   id:ID!
		   firstName:String
		   lastName:String
		   fullName:String
		   college:College
		}

		type College {
		   id:ID!
		   name:String
		   location:String
		   rating:Float
		   students:[Student]
		}

	4. Move faster with powerful developer tools

		GraphQL provides rich developer tools for documentation and testing queries. 
		GraphiQL is an excellent tool which generates documentation of the query and its schema. 


How to Build a GraphQL server with Nodejs

	Create a Project Folder "graphqlServer"

	Create package.json and Install the Dependencies 

		npm install express

	Install GraphQL using the following command. We will be installing graphql and graphql for express.

		npm install express-graphql graphql

	Create Schema File

	Create Resolver File

	Create Server.js and Configure GraphQL


GraphQL - Architecture
	GraphQL Server with Connected Database

		https://www.tutorialspoint.com/graphql/graphql_architecture.htm
	GraphQL Server Integrating Existing Systems
		https://www.tutorialspoint.com/graphql/graphql_architecture.htm

GraphQL - Type System
	GraphQL is a strongly typed language. Type System defines various data types that can be used in a GraphQL application. The type system helps to define the schema, which is a contract between client and server. The commonly used GraphQL data types are as follows −
	
	Scalar Type :

		Scalar types are primitive data types that can store only a single value. The default scalar types that GraphQL offers are −

		Int − Signed 32-bit Integer

		Float − Signed double precision floating point value

		String − UTF - 8-character sequence

		Boolean − True or false

		ID − A unique identifier, often used as a unique identifier to fetch an object or as the key for a cache.

		The syntax for defining a scalar type is as follows −

		field: data_type

		greeting: String

	Object Type :

			The object type is the most common type used in a schema and represents a group of fields. Each field inside an object type maps to another type, thereby allowing nested types.

		You can consider the following code snippet −

		--Define an object type--

			type Student {
			   stud_id:ID
			   firstname: String
			   age: Int
			   score:Float
			}

		--Defining a GraphQL schema--  

			type Query
			{
			   stud_details:[Student]
			}


	Query Type : 

		A GraphQL query is used to fetch data. It is like requesting a resource in REST-based APIs.GraphQL uses the Schema Definition Language (SDL) to define a Query.
		The syntax for defining a Query is as given below −

		type Query {
		   field1: data_type
		   field2:data_type
		   field2(param1:data_type,param2:data_type,...paramN:data_type):data_type
		}

	Mutation Type :

		Mutations are operations sent to the server to create, update or delete data. These are analogous to the PUT, POST, PATCH and DELETE verbs to call REST-based APIs.
		For example, we can define a mutation type to add a new Student as below −

		type Mutation {
		   addStudent(firstName: String, lastName: String): Student
		}

	Non-Nullable Type : 
		Exclamation mark (!) can be appended to a type

		In the below example, stud_id is declared as a mandatory field.

		type Student {
		   stud_id:ID!
		   firstName:String
		   lastName:String
		   fullName:String
		   college:College
		}

	Enum Type : 
		An Enum is similar to a scalar type.

	List Type:
		Lists can be used to represent an array of values of specific type.

		The below example defines a list type todos −
		type Query {
		   todos: [String]
		}

GraphQL - Schema

	A GraphQL schema is at the core of any GraphQL server implementation. It describes the functionality available to the client applications that connect to it. We can use any programming language to create a GraphQL schema and build an interface around it.


GraphQL - Resolver
	Resolver is a collection of functions that generate response for a GraphQL query.

GraphQL - Query


GraphQL - Validation

GraphQL - Authenticating Client
  
  
