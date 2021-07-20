# GraphQL

Strongly typed query language and runtime for your data created by facebook.

## Types

-   Scalar

    -   Int: A signed 32-bit integer
    -   Float: A signed double precision floating point value
    -   String: A UTF-8 character sequence
    -   Boolean: true or false
    -   ID: a unique identifier serialized as a string

-   Object

    -   Most of the types you define in graphql schema are object types. An object type contains a collection of fields each of which can be either a scalar or another object type.

-   Query

    -   Defines exactly which graphql queries client can execute against your data graph. It resembles an object type but its name is always Query

    ```javascript
    type Query {
      getBooks: [Book]
      getAuthors: [Author]
    }

    // This Query type defines two available queries: getBooks and getAuthors. Each query returns a list of the corresponding type.

    // With a REST-based API, books and authors would probably be returned by different endpoints (e.g., /api/books and /api/authors). The flexibility of GraphQL enables clients to query both resources with a single request.
    ```

    -   Mutation

        -   Similar in structure and purpose as Query type. The mutation type defines supported write operations

        ```javascript
        type Mutation {

        addBook(title: String, author: String): Book
        }

        // This Mutation type defines a single available mutation, addBook. The mutation accepts two arguments (title and author) and returns a newly created Book object. As you'd expect, this Book object conforms to the structure that we defined in our schema.
        ```

    -   Input Type

    -   Special object types that allow you to pass objects as arguments to queries and mutations.

    ```javascript
    type Mutation {
      createPost(post: PostAndMediaInput): Post
    }

    input PostAndMediaInput {
      title: String
      body: String
      mediaUrls: [String]
    }
    ```
