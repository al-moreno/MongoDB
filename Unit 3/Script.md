# Module 3: MongoDB Data Modeling

## Table of Contents
1. Collections and Documents data model
2. BSON format and data types
3. Schema design principles and best practices
4. Embedded documents vs. referencing
5. One-to-one, one-to-many, and many-to-many relationships
6. Assessment



## Collections & Documents
- Slide 1 - 
Welcome to your second lesson on MongoDB. We're glad to have you back!

- Slide 2 -

In this module, we will cover a range of essential objectives related to MongoDB's data model and schema design some of which we briefly touched on in the previous lesson. We will start by exploring the Collections and Documents data model, understanding how data is organized and stored within MongoDB. Next, we will dive into the BSON format and various data types supported by MongoDB, equipping you with the knowledge to effectively work with data in this format. We will then delve into schema design principles and best practices, guiding you on how to structure your data efficiently and optimize performance. Additionally, we will discuss the pros and cons of using embedded documents versus referencing, enabling you to make informed decisions when designing your schema. Finally, we will explore different types of relationships, including one-to-one, one-to-many, and many-to-many, and learn how to model them effectively in MongoDB. By the end of this module, you will have a comprehensive understanding of MongoDB's data model, schema design considerations, and how to manage relationships within your data.



- Slide 3 - 

In MongoDB, data is organized into collections and documents. Collections are similar to tables in relational databases, as they serve as containers for storing related data. Each collection can contain multiple documents, which are comparable to records or rows in relational databases.

Documents in MongoDB are JSON-like data structures that store information. They consist of key-value pairs, where the keys represent the field names, and the values store the corresponding data. Documents within a collection can have different structures, allowing flexibility in the data model. This contrasts with relational databases, where tables enforce a fixed schema for all records.

Parallels can be drawn between collections and tables, as both serve as containers for data storage. Similarly, documents and records represent individual instances of data within these containers. However, MongoDB's document-oriented approach offers more flexibility in terms of data modeling and schema design compared to the structured nature of tables and records in relational databases.

Overall, collections and documents in MongoDB provide a flexible and adaptable way to store and retrieve data, allowing developers to work with diverse data structures more efficiently.

- Slide 4 - 

Let's consider an example to understand the concept of the Collections and Documents data model in MongoDB. Imagine we are building an digital library catalog platform.

In MongoDB, we would create a collection called "Books" to store all the various title for books. Each individual book would be represented as a document within the Books collection.


A document in MongoDB is similar to a JSON object and consists of key-value pairs. For instance, a document for a  book might have fields like "title," "author," "pages," and "rating." The values for these fields would contain the specific information for each book, such as the title of the book, the author's name, the number of pages or its rating.


With the Collections and Documents data model, we can easily add, modify, and retrieve books. Each document within the "Books" collection can have a different structure if needed, allowing flexibility in the data model. For example, some books may have additional fields like "Category" or "Date Published," while others may not.

By utilizing the Collections and Documents data model in MongoDB, we can organize and store our books in a scalable and efficient manner, making it easier to manage and query our data.

- Slide 5 - 


In the previous slide, we provided an example of a document whose content was in BSON format. BSON stands for Binary JSON, which is the binary representation format used by MongoDB to store and transmit data. It is designed to be efficient, compact, and fast to parse, making it well-suited for a document-based data model.

BSON supports a wide range of data types, allowing for the representation of diverse information within MongoDB documents. Here are some commonly used data types in MongoDB:

1. MongoDB supports various string types, including regular strings (UTF-8 encoded), binary data, and UUIDs.

2. It also supports different numeric data types, such as integers (32-bit and 64-bit), floating-point numbers, and decimal data types for precise arithmetic operations.

3. It also provides a Boolean data type for representing true or false values.

4. Additonally, MongoDB supports storing dates and timestamps. Dates are represented as a 64-bit integer value, which represents the number of milliseconds since the time of Unix (January 1, 1970).

5. MongoDB allow for the storage of multiple values within a single field. They can contain values of different data types and can be nested to create multi-dimensional arrays.

6. It enables the the nesting of documents within other documents, enabling the creation of hierarchical and complex data structures. This feature is useful for representing relationships or grouping related data.

In addition to these basic data types, BSON also supports more specialized data types, such as geospatial data, binary data, regular expressions, and timestamps enabling MongoDB to handle diverse data structures and accommodate the needs of various applications. 



- Slide 6 -

When designing MongoDB schemas, there are several important considerations and best practices to ensure effectiveness, scalability, and optimal performance. Here are some key aspects to keep in mind:

1. Design your schema with scalability in mind. Consider the anticipated data growth and the expected workload. Use sharding to distribute data across multiple servers or clusters, allowing for horizontal scaling. Plan your indexes carefully to support efficient queries and avoid performance bottlenecks.

2. Determine the relationships between your data and choose an appropriate data modeling approach. MongoDB supports embedded documents and referencing. Use embedding for one-to-one or one-to-many relationships where the related data is frequently accessed together. Use referencing for many-to-many relationships or when the related data is large and accessed infrequently. Strive for a balance between denormalization for performance and normalization for data integrity.

3. Understand the read-and-write patterns of your application. Optimize your schema design to align with the most frequent operations. Consider the data access patterns and design indexes accordingly to support efficient queries. Use the appropriate write concern and read preference settings based on your application's requirements.

4. Standardize your schema when necessary to improve read performance. By embedding related data in a single document, you can retrieve all necessary information in one query, reducing the need for joins. However, be mindful of potential data duplication and the trade-off between query performance and data consistency.

5. Design indexes based on your application's query patterns. Create indexes for frequently queried fields and for fields involved in sorting or filtering operations. Ensure your indexes fit in memory to avoid disk accesses, which can significantly impact performance.

6. Anticipate future data growth and evolving requirements. Design your schema to accommodate future changes without major disruptions. Consider the impact of schema modifications on existing data and plan for migration strategies if needed.

7. Regularly monitor the performance of your MongoDB deployment. Utilize MongoDB's profiling and monitoring tools to identify bottlenecks and optimize query performance. Continuously refine and improve your schema design based on real-world usage patterns.

By considering these best practices and aligning your schema design with your application's requirements, you can create effective MongoDB schemas that promote scalability, performance, and adaptability to evolving data needs.


- Slide 7 - 

When deciding between embedding documents within other documents or referencing them in MongoDB, it's important to consider the trade-offs in performance, query complexity, and data integrity. Here are the pros and cons of each approach:

Here are the pros for Embedding Documents:


1. Embedded documents can be retrieved in a single query, reducing the need for complex joins and improving read performance.
2. With embedded documents, related data is stored together, making it easier and faster to access all necessary information.
3. Embedding allows for flexible and dynamic schema design, as documents within a collection can have different structures.

The cons for Embedding documents consist of:

1. Embedding documents can result in data duplication if the same information is repeated in multiple documents, leading to increased storage requirements.
2. If data needs to be updated across multiple documents, it can lead to update anomalies and the potential for inconsistent data if not carefully managed.
3. Embedding documents may limit scalability when dealing with large amounts of related data, as the document size can become unwieldy.

Next we'll consider the pros and cons for Referencing Documents.
We'll begin with the pros:


1. Referencing promotes data normalization by storing related data in separate collections, reducing data redundancy and ensuring consistency.
2. Updates to referenced data only need to be performed in one place, reducing the risk of inconsistencies and update anomalies.
3. Referencing can handle large amounts of related data more efficiently, as the document size remains manageable.

The cons for Reference documents consis of:

1. Referencing requires additional queries and joins to retrieve related data, resulting in increased query complexity and potentially impacting performance.
2. Referencing can lead to slower read performance due to the need for multiple queries and joins to fetch all required data.
3. Referencing adds additional overhead in terms of maintaining relationships, managing foreign keys, and handling multiple queries.


Ultimately, the choice between embedding and referencing depends on factors such as the nature of the data relationships, the frequency of data access, the size of related data, and the specific performance requirements of the application. Striking a balance between denormalization for performance gains and normalization for data integrity is crucial in designing an effective MongoDB schema.



- Slide 8 - 

In MongoDB, modeling relationships means designing data structure to represent connections between entities. It determines how documents in collections are related and how these relationships are represented in the database.

We've discussed the benefits of modeling relationships include logical and efficient storage and retrieval of related data, ensuring data integrity, and facilitating efficient querying. It allows defining connections and interactions between different entities in the application.

There are two approaches to modeling relationships in MongoDB: embedding and referencing. Embedding involves nesting related data within a document, while referencing stores references or identifiers to related documents.

Accurate modeling and appropriate approach selection (embedding or referencing) ensure efficient data organization, retrieval, and manipulation. It enables representation of complex data structures and accurate reflection of entity relationships in the application.

Next, we'll explore the various relationship models which include one-to-one, one-to-many, and many-to-many relationships. 



- Slide 9 -


In a one-to-one relationship, each document is uniquely associated with another document. Taking the example of the student and address documents, a student can have only one address at a time. Assuming each household has only one student, the address listed for each student becomes a unique identifier, establishing a relationship between the two document. This unique address can be utilized to create a one-to-one relationship.


- Slide 10 - 


In a one-to-many relationship, one document is associated with multiple related documents. Taking the example of the student and the address document examples. one student can have many phone numbers.

- Slide 11 - 


In a many-to-many relationship refers to a scenario where multiple documents are connected to multiple other documents as we see on the example. 

So, having covered the theoretical concepts of collections and document data models, explored the BSON format and various data types, examined principles of schema design and best practices, along with having discussed different types of relationships, we are ready to dive into a hands on walthrough of the topics discussed so as to allow us to obtain the practice need. I'll see you on our next lesson. 







## Collections and Documents data model

As we learned in the previous lesson, data is organized and stored in collections and documents. Collections are similar to tables in relational databases, as they serve as containers for related data. Each collection can contain multiple documents, which are comparable to records or rows in relational databases.

The concept of collections and documents can be understood by considering a bookstore application. In a relational database, you might have a "Books" table where each row represents a book with columns for attributes like title, author, and ISBN. In MongoDB, you would create a collection called "Books" to store these books. Each individual book would be represented as a document within the "Books" collection.

Here's an example of a document in the "Books" collection in MongoDB:

```javascript
{
  "_id": ObjectId("60eae773eae9f94db6a69cf4"),
  "title": "The Great Gatsby",
  "author": "F. Scott Fitzgerald",
  "isbn": "978-0-684-80146-3",
  "price": 10.99
}
```

In this example, each field in the document represents an attribute of the book, such as title, author, ISBN, and price. The `_id` field is a unique identifier automatically generated by MongoDB.

The similarities between tables and collections can be drawn as both serve as containers for data storage. Similarly, documents and records represent individual instances of data within these containers. In fact, if we export the content of one of our current databases we may find more clarity in this comparison.

Overall, the concept of collections and documents in MongoDB provides a flexible and adaptable way to store and retrieve data, allowing developers to work with diverse data structures more efficiently.



## BSON format and data types

Continuing on with BSON, which stands for Binary JSON, it is the binary representation format used by MongoDB to store and transmit data. It is designed to be efficient, compact, and fast to parse, making it well-suited for a document-based data model.

We mentioned previously that MongoDB supports various data types within BSON, allowing for the representation of diverse information within documents. Here are some commonly used data types supported by MongoDB:

1. MongoDB supports different types of strings, including regular strings (UTF-8 encoded), binary data, and UUIDs. Strings are used to store textual information and are eclosed in quotes.

Example:
```javascript
{
  "name": "John Doe",
  "email": "john@example.com",
  "bio": "Lorem ipsum dolor sit amet"
}
```

2. MongoDB also supports different numeric data types, such as integers (32-bit and 64-bit), floating-point numbers, and decimal data types for precise arithmetic operations. Numbers are used to store numerical values.

Example:
```javascript
{
  "age": 25,
  "price": 9.99,
  "quantity": 10
}
```

3. We also have available a Boolean data type for representing true or false values. Booleans are used for logical operations and conditional expressions.

Example:
```javascript
{
  "isAvailable": true,
  "isAdmin": false
}
```

4. MongoDB supports storing dates and timestamps. Dates are represented as a 64-bit integer value, which represents the number of milliseconds since the time of Unix (January 1, 1970). Dates are used for storing temporal information.

Example:
```javascript
{
  "createdAt": ISODate("2022-07-01T10:00:00Z"),
}
```



5. Next, we'll look at arrays which allow for the storage of multiple values within a single field. They can contain values of different data types and can be nested to create multi-dimensional arrays.

Example:
```javascript
{
  "tags": ["mongodb", "database", "nosql"],
  "scores": [80, 85, 90, 95]
}
```

6. We have heard on several occations that MongoDB also allows for the nesting of documents within other documents, enabling the creation of hierarchical and complex data structures. This feature is useful for representing relationships or grouping related data.

Example:
```javascript
{
  "name": "John Doe",
  "address": {
    "street": "123 Main St",
    "city": "New York",
    "state": "NY",
    "zipcode": "10001"
  }
}
```

In addition to these basic data types, BSON also supports more specialized data types, such as geospatial data, binary data, regular expressions, and timestamps, I would encourage you to research some of these data types further.

By supporting a wide range of data types, BSON enables MongoDB to handle diverse data structures and accommodate the needs of various applications. 


## Schema design principles and best practices && Embedded documents vs. referencing

We will continue our dicsuccion of schema desing priciples and best bractices in combination with that of embeded documents vs referencing to get a solid undertanding of how we apply and take the various concepts into account. We stated that when considering the design of an effective schema, it is necessary to anticiplate scalability, data relationship and read/write patters. Let's elaborate a bit on these concept with some examples.

The scenario for our example will be the following: We are developing a social media platform where users can post and comment on each other's posts. Our application is expected to experience significant growth in both user activity and data volume. We need to design an effective MongoDB schema to handle scalability, data relationships, and read/write patterns efficiently.

Note from the scenario: 

Requirements:
- We have two main entities: User and Post and each post can have multiple comments.
- Each User document should contain fields for "username," "name," and "email."
- Each Post document should contain fields for "content," "likes," "comments," and "timestamp."
- 

Goal:
- Our goal is to optimize the schema for efficient data access and updates while considering potential scalability and performance trade-offs.

1. Start by sketching out two schema designs: one using embedding and the other using referencing. Include the necessary fields for each entity (User, and Post) and their relationships.
2. For the embedded schema, consider how the User and Comment information will be stored within the Post document. Analyze how this design simplifies data access and impacts read performance.
3. For the referencing schema, we need to decide how the relationships between Post, and User will be established using references. Consider how this design promotes data normalization and facilitates efficient updates.
4. Consider the trade-offs of each schema design, highlighting the advantages and disadvantages mentioned in the content above. Consider factors such as data duplication, update anomalies, query complexity, and read performance.

```javascript
// User Collection:
{
  _id: ObjectId("user_id"),
  name: "User Name",
  username: "username",
  email: "user@email.com",
  // Other user details
}

// Post Collection:
{
  _id: ObjectId("post_id"),
  user_id: ObjectId("user_id"),
  content: "Post content",
  likes: 0,
  //We'll instead want to embed comments to improve read performanc when displaying a post with a comment. 
  comments: [
    {
      // I will create a reference to the user_id to minimize addional quiring when showing post authors. 
      _id: ObjectId("comment_id"),
      user_id: ObjectId("user_id"),
      content: "Comment content",
      timestamp: ISODate("2023-07-06T12:34:56.789Z")
    },
    // More comments
  ],
  timestamp: ISODate("2023-07-06T12:00:00.000Z")
}

```

Remember to continuously monitor your application's performance, make necessary schema optimizations, and adapt the design to changing data needs as your social media platform grows.




## One-to-one, one-to-many, and many-to-many relationships




In MongoDB, we can model different types of relationships between documents, including one-to-one, one-to-many, and many-to-many relationships. Let's explore each of these scenarios and demonstrate how to model them:

1. In a one-to-one relationship, each document is uniquely associated with another document. This type of relationship is represented by embedding the related data within the same document.

Example:
Consider a scenario where we have a "user" document and a "profile" document, where each user has one profile associated with them. You can model this relationship by embedding the profile information within the user document. The structure would look like:

```javascript
{
  "_id": "user1",
  "name": "John",
  "email": "john@example.com",
  "profile": {
    "dob": "1990-01-01",
    "gender": "Male",
    "address": "123 Main St"
  }
}
```

2. In a one-to-many relationship, one document is associated with multiple related documents. This type of relationship is represented by embedding an array of related documents or by referencing the related documents.

Example:
Consider a scenario where we have a "category" document and multiple "product" documents within that category. We can model this relationship by either embedding the product documents within the category document as an array or 

Embedding:
```javascript
{
  "_id": "category1",
  "name": "Electronics",
  "products": [
    { "name": "TV", "price": 1000 },
    { "name": "Phone", "price": 800 }
  ]
}
```

Referencing:
Or we can model this relationship by referencing the product documents using their unique identifiers.
```javascript
// category document
{
  "_id": "category1",
  "name": "Electronics"
}

// product documents
{
  "_id": "product1",
  "name": "TV",
  "price": 1000,
  "category_id": "category1"
}
{
  "_id": "product2",
  "name": "Phone",
  "price": 800,
  "category_id": "category1"
}
```

3. In a many-to-many relationship, multiple documents are connected to multiple other documents. This type of relationship is represented by referencing the related documents using arrays in both directions.

Example:
Let's say we have a "student" document and a "course" document, where each student can be enrolled in multiple courses, and each course can have multiple students. We can model this relationship by maintaining an array of student references in the course document and an array of course references in the student document.

```javascript
// student document
{
  "_id": "student1",
  "name": "Alice",
  "courses": ["course1", "course2"]
}

// course document
{
  "_id": "course1",
  "name": "Math",
  "students": ["student1", "student2"]
}
```

By using these modeling techniques, we can effectively represent and manage different types of relationships. Recall that the approach we choose depends on factors such as the nature of the relationship, the frequency of data access, and the performance requirements of our application.


## Assessment


1. Which of the following best describes the purpose of collections and documents in MongoDB?
   a. Collections store related data, while documents represent individual instances of data within the collections.
   b. Collections store individual instances of data, while documents group related data together.
   c. Collections and documents are interchangeable terms in MongoDB.
   d. Collections store data types, while documents define the structure of the data.

2. What is BSON in MongoDB?
   a. A query language used to retrieve data from MongoDB.
   b. A data modeling approach for organizing documents in collections.
   c. A binary representation format used to store and transmit data in MongoDB.
   d. A tool for creating indexes to optimize query performance in MongoDB.

3. Which of the following is NOT a commonly used data type in MongoDB?
   a. Strings
   b. Numbers
   c. Dates
   d. Documents

4. What is an advantage of embedding documents in MongoDB?
   a. Improved read performance
   b. Reduced data duplication
   c. Efficient handling of large amounts of related data
   d. Simplified querying through joins

5. When should referencing documents be preferred over embedding in MongoDB?
   a. For one-to-one relationships with infrequent data access
   b. For one-to-many relationships with frequent data access
   c. For many-to-many relationships with large amounts of related data
   d. For any type of relationship regardless of data characteristics

6. Which of the following is NOT an important consideration when designing MongoDB schemas?
   a. Scalability
   b. Data normalization
   c. Read-and-write patterns of the application
   d. Authentication and security measures

7. In a one-to-one relationship, each document is uniquely associated with:
   a. Multiple other documents
   b. One document from another collection
   c. One document from the same collection
   d. Multiple collections

8. In a one-to-many relationship, one document is associated with:
   a. Multiple other documents
   b. One document from another collection
   c. One document from the same collection
   d. Multiple collections

9. What are the benefits of modeling relationships in MongoDB?
   a. Efficient storage and retrieval of related data
   b. Improved performance of complex queries
   c. Ensuring data integrity
   d. All of the above

10. What does a many-to-many relationship in MongoDB refer to?
    a. A scenario where multiple documents are connected to multiple other documents
    b. A scenario where multiple documents are connected to a single document
    c. A scenario where a single document is connected to multiple collections
    d. A scenario where a single document is connected to a single collection

Correct answers:
1. a
2. c
3. d
4. a
5. c
6. d
7. c
8. a
9. d
10. a