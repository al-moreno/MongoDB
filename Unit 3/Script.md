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

Embedding Documents:
Pros:

1. Improved Read Performance: Embedded documents can be retrieved in a single query, reducing the need for complex joins and improving read performance.
2. Simplified Data Access: With embedded documents, related data is stored together, making it easier and faster to access all necessary information.
3. Schema Flexibility: Embedding allows for flexible and dynamic schema design, as documents within a collection can have different structures.

Cons:

1. Data Duplication: Embedding documents can result in data duplication if the same information is repeated in multiple documents, leading to increased storage requirements.
2. Update Anomalies: If data needs to be updated across multiple documents, it can lead to update anomalies and the potential for inconsistent data if not carefully managed.
3. Limited Scalability: Embedding documents may limit scalability when dealing with large amounts of related data, as the document size can become unwieldy.

Referencing Documents:
Pros:

1. Data Normalization: Referencing promotes data normalization by storing related data in separate collections, reducing data redundancy and ensuring consistency.
2. Efficient Updates: Updates to referenced data only need to be performed in one place, reducing the risk of inconsistencies and update anomalies.
3. Scalability: Referencing can handle large amounts of related data more efficiently, as the document size remains manageable.

Cons:

1. Increased Query Complexity: Referencing requires additional queries and joins to retrieve related data, resulting in increased query complexity and potentially impacting performance.
2. Reduced Read Performance: Referencing can lead to slower read performance due to the need for multiple queries and joins to fetch all required data.
3. Additional Overhead: Referencing adds additional overhead in terms of maintaining relationships, managing foreign keys, and handling multiple queries.


Ultimately, the choice between embedding and referencing depends on factors such as the nature of the data relationships, the frequency of data access, the size of related data, and the specific performance requirements of the application. Striking a balance between denormalization for performance gains and normalization for data integrity is crucial in designing an effective MongoDB schema.



- Slide 8 - 

In MongoDB, modeling relationships means designing data structure to represent connections between entities. It determines how documents in collections are related and how these relationships are represented in the database.

Benefits of modeling relationships include logical and efficient storage and retrieval of related data, ensuring data integrity, and facilitating efficient querying. It allows defining connections and interactions between different entities in the application.

There are two approaches to modeling relationships in MongoDB: embedding and referencing. Embedding involves nesting related data within a document, while referencing stores references or identifiers to related documents.

Accurate modeling and appropriate approach selection (embedding or referencing) ensure efficient data organization, retrieval, and manipulation. It enables representation of complex data structures and accurate reflection of entity relationships in the application.

Next, we'll explore the various relationship models which include one-to-one, one-to-many, and many-to-many relationships. 



- Slide 9 -


One-to-One Relationship:
In a one-to-one relationship, each document is uniquely associated with another document. Taking the example of the student and address documents, a student can have only one address at a time. Assuming each household has only one student, the address listed for each student becomes a unique identifier, establishing a relationship between the two document. This unique address can be utilized to create a one-to-one relationship.


- Slide 10 - 


One-to-Many Relationship:
In a one-to-many relationship, one document is associated with multiple related documents. Taking the example of the student and the address document examples. one student can have many phone numbers.

- Slide 11 - 

Many-to-Many Relationship:



In MongoDB, a many-to-many relationship refers to a scenario where multiple documents are connected to multiple other documents.

Now that we have covered the theoretical concepts of collections and document data models, explored the BSON format and various data types, examined principles of schema design and best practices, and discussed different types of relationships, we are ready to dive into a live demonstration. This hands-on session will allow us to put these concepts into practice and see them in action.







## Collections and Documents data model

In MongoDB, data is organized and stored in collections and documents. Collections are similar to tables in relational databases, as they serve as containers for related data. Each collection can contain multiple documents, which are comparable to records or rows in relational databases.

The concept of collections and documents can be understood through an example. Let's consider a bookstore application. In a relational database, you might have a "Books" table where each row represents a book with columns for attributes like title, author, and ISBN. In MongoDB, you would create a collection called "Books" to store these books. Each individual book would be represented as a document within the "Books" collection.

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

The parallel between tables and collections can be drawn as both serve as containers for data storage. Similarly, documents and records represent individual instances of data within these containers. However, MongoDB's document-oriented approach offers more flexibility in terms of data modeling and schema design compared to the structured nature of tables and records in relational databases.

Overall, the concept of collections and documents in MongoDB provides a flexible and adaptable way to store and retrieve data, allowing developers to work with diverse data structures more efficiently.



## BSON format and data types

BSON, which stands for Binary JSON, is the binary representation format used by MongoDB to store and transmit data. It is designed to be efficient, compact, and fast to parse, making it well-suited for a document-based data model.

MongoDB supports various data types within BSON, allowing for the representation of diverse information within documents. Here are some commonly used data types supported by MongoDB:

1. Strings: MongoDB supports different types of strings, including regular strings (UTF-8 encoded), binary data, and UUIDs. Strings are used to store textual information.

Example:
```javascript
{
  "name": "John Doe",
  "email": "john@example.com",
  "bio": "Lorem ipsum dolor sit amet"
}
```

2. Numbers: MongoDB supports different numeric data types, such as integers (32-bit and 64-bit), floating-point numbers, and decimal data types for precise arithmetic operations. Numbers are used to store numerical values.

Example:
```javascript
{
  "age": 25,
  "price": 9.99,
  "quantity": 10
}
```

3. Booleans: MongoDB provides a Boolean data type for representing true or false values. Booleans are used for logical operations and conditional expressions.

Example:
```javascript
{
  "isAvailable": true,
  "isAdmin": false
}
```

4. Dates: MongoDB supports storing dates and timestamps. Dates are represented as a 64-bit integer value, which represents the number of milliseconds since the time of Unix (January 1, 1970). Dates are used for storing temporal information.

Example:
```javascript
{
  "createdAt": ISODate("2022-07-01T10:00:00Z"),
  "updatedAt": ISODate("2022-07-05T15:30:00Z")
}
```

5. Arrays: Arrays in MongoDB allow for the storage of multiple values within a single field. They can contain values of different data types and can be nested to create multi-dimensional arrays.

Example:
```javascript
{
  "tags": ["mongodb", "database", "nosql"],
  "scores": [80, 85, 90, 95]
}
```

6. Embedded Documents: MongoDB allows for the nesting of documents within other documents, enabling the creation of hierarchical and complex data structures. This feature is useful for representing relationships or grouping related data.

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

In addition to these basic data types, BSON also supports more specialized data types, such as geospatial data, binary data, regular expressions, and timestamps.

By supporting a wide range of data types, BSON enables MongoDB to handle diverse data structures and accommodate the needs of various applications. It provides a flexible and efficient way to represent and store data within MongoDB's document-oriented model.


## Schema design principles and best practices


When designing effective MongoDB schemas, it is crucial to consider various factors such as scalability, data relationships, and read/write patterns. Here are some important considerations and best practices:

1. Scalability:
   - Plan for future growth: Anticipate the data growth and workload of your application. Design your schema to scale horizontally by utilizing sharding, which distributes data across multiple servers or clusters.
   - Index optimization: Regularly review and optimize indexes to improve query performance. Identify frequently queried fields and create indexes for them. Consider the trade-off between index size and query performance.

Example:
If you have an e-commerce application, you can create indexes on frequently accessed fields like product names, categories, or customer IDs to speed up search queries.

2. Data Relationships:
   - Determine relationship types: Identify the relationships between different data entities, such as one-to-one, one-to-many, or many-to-many.
   - Embedding vs. referencing: Choose the appropriate data modeling approach based on the nature of relationships. Use embedding when related data is frequently accessed together, and referencing when dealing with large amounts of related data or many-to-many relationships.

Example:
In an online marketplace, embedding product information within an order document makes sense as the order and product details are frequently accessed together. However, referencing customer information in the order document may be more appropriate for managing large customer datasets.

3. Read/Write Patterns:
   - Understand data access patterns: Analyze the read and write patterns of your application. Optimize your schema design to align with the most frequent operations.
   - Data denormalization: Consider denormalizing data for improved read performance. By embedding related data within a document, you can retrieve all necessary information in one query, reducing the need for joins.

Example:
For a blogging platform, embedding comments within a blog post document allows fetching the entire post along with its comments in a single query, improving read performance.

These considerations and best practices ensure effective MongoDB schema design that promotes scalability, performance, and adaptability to evolving data needs. Remember that schema design depends on the specific requirements of your application, and it may evolve over time as your application evolves. It's essential to regularly monitor the performance of your MongoDB deployment, make necessary optimizations, and refine your schema based on real-world usage patterns.


## Embedded documents vs. referencing

When it comes to designing MongoDB schemas, one important decision is whether to embed documents within other documents or reference them. Let's explore the pros and cons of each approach and the trade-offs involved:

1. Embedding Documents:
   Pros:
   - Improved Read Performance: Embedded documents can be retrieved in a single query, reducing the need for complex joins and improving read performance.
   - Simplified Data Access: With embedded documents, related data is stored together, making it easier and faster to access all necessary information.
   - Schema Flexibility: Embedding allows for flexible and dynamic schema design, as documents within a collection can have different structures.

   Cons:
   - Data Duplication: Embedding documents can result in data duplication if the same information is repeated in multiple documents, leading to increased storage requirements.
   - Update Anomalies: If data needs to be updated across multiple documents, it can lead to update anomalies and the potential for inconsistent data if not carefully managed.
   - Limited Scalability: Embedding documents may limit scalability when dealing with large amounts of related data, as the document size can become unwieldy.

Example:
In an e-commerce application, embedding customer information within an order document can provide quick access to all relevant details like name, address, and contact information. However, if a customer updates their address, it needs to be updated in all related order documents, which can be cumbersome and potentially error-prone.

2. Referencing Documents:
   Pros:
   - Data Normalization: Referencing promotes data normalization by storing related data in separate collections, reducing data redundancy and ensuring consistency.
   - Efficient Updates: Updates to referenced data only need to be performed in one place, reducing the risk of inconsistencies and update anomalies.
   - Scalability: Referencing can handle large amounts of related data more efficiently, as the document size remains manageable.

   Cons:
   - Increased Query Complexity: Referencing requires additional queries and joins to retrieve related data, resulting in increased query complexity and potentially impacting performance.
   - Reduced Read Performance: Referencing can lead to slower read performance due to the need for multiple queries and joins to fetch all required data.
   - Additional Overhead: Referencing adds additional overhead in terms of maintaining relationships, managing foreign keys, and handling multiple queries.

Example:
In a content management system, referencing author information in a separate collection allows for more efficient updates to author details across multiple articles. However, fetching an article along with its author requires querying both the article and author collections, adding complexity to the retrieval process.

The choice between embedding and referencing depends on factors such as the nature of the data relationships, the frequency of data access, the size of related data, and the specific performance requirements of the application. Striking a balance between denormalization for performance gains and normalization for data integrity is crucial in designing an effective MongoDB schema. It's important to carefully analyze your application's requirements and consider the trade-offs before making a decision.


## One-to-one, one-to-many, and many-to-many relationships




In MongoDB, you can model different types of relationships between documents, including one-to-one, one-to-many, and many-to-many relationships. Let's explore each of these scenarios and demonstrate how to model them in MongoDB:

1. One-to-One Relationship:
   In a one-to-one relationship, each document is uniquely associated with another document. This type of relationship is represented by embedding the related data within the same document.

Example:
Let's consider a scenario where you have a "user" document and a "profile" document, where each user has one profile associated with them. You can model this relationship by embedding the profile information within the user document. The structure would look like:

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

2. One-to-Many Relationship:
   In a one-to-many relationship, one document is associated with multiple related documents. This type of relationship is represented by embedding an array of related documents or by referencing the related documents.

Example:
Consider a scenario where you have a "category" document and multiple "product" documents within that category. You can model this relationship by either embedding the product documents within the category document as an array or by referencing the product documents using their unique identifiers.

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

3. Many-to-Many Relationship:
   In a many-to-many relationship, multiple documents are connected to multiple other documents. This type of relationship is represented by referencing the related documents using arrays in both directions.

Example:
Let's say you have a "student" document and a "course" document, where each student can be enrolled in multiple courses, and each course can have multiple students. You can model this relationship by maintaining an array of student references in the course document and an array of course references in the student document.

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

By using these modeling techniques, you can effectively represent and manage different types of relationships in MongoDB. The approach you choose depends on factors such as the nature of the relationship, the frequency of data access, and the performance requirements of your application.





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