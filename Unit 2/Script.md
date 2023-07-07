# Module 2: MongoDB Data Modeling

## Table of Contents
1. Collections and Documents data model
2. BSON format and data types
3. Schema design principles and best practices
4. Embedded documents vs. referencing
5. One-to-one, one-to-many, and many-to-many relationships



## Collections & Documents
- Slide 1 - 
Welcome to your second lesson on MongoDB. We're glad to have you back!

- Slide 2 -

In this module, we will cover a range of essential objectives related to MongoDB's data model and schema design. We will start by exploring the Collections and Documents data model, understanding how data is organized and stored within MongoDB. Next, we will dive into the BSON format and various data types supported by MongoDB, equipping you with the knowledge to effectively work with data in this format. We will then delve into schema design principles and best practices, guiding you on how to structure your data efficiently and optimize performance. Additionally, we will discuss the pros and cons of using embedded documents versus referencing, enabling you to make informed decisions when designing your schema. Finally, we will explore different types of relationships, including one-to-one, one-to-many, and many-to-many, and learn how to model them effectively in MongoDB. By the end of this module, you will have a comprehensive understanding of MongoDB's data model, schema design considerations, and how to manage relationships within your data.



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

1. Strings: MongoDB supports various string types, including regular strings (UTF-8 encoded), binary data, and UUIDs.

2. Numbers: MongoDB supports different numeric data types, such as integers (32-bit and 64-bit), floating-point numbers, and decimal data types for precise arithmetic operations.

3. Booleans: MongoDB provides a Boolean data type for representing true or false values.

4. Dates: MongoDB supports storing dates and timestamps. Dates are represented as a 64-bit integer value, which represents the number of milliseconds since the time of Unix (January 1, 1970).

5. Arrays: Arrays in MongoDB allow for the storage of multiple values within a single field. They can contain values of different data types and can be nested to create multi-dimensional arrays.

6. Embedded Documents: MongoDB allows for the nesting of documents within other documents, enabling the creation of hierarchical and complex data structures. This feature is useful for representing relationships or grouping related data.

In addition to these basic data types, BSON also supports more specialized data types, such as geospatial data, binary data, regular expressions, and timestamps.

By supporting a wide range of data types, BSON enables MongoDB to handle diverse data structures and accommodate the needs of various applications. It provides a flexible and efficient way to represent and store data within MongoDB's document-oriented model.


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




















