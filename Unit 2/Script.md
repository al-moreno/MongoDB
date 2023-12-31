# Module 2: MongoDB Tools

## Table of Contents
1. Running MongoDB service for macOS and Windows
2. MongoDB Shell (GUI tool) 
3. MongoDB Compass (GUI tool) 
4. Managing databases, collections, and documents
5. Assessment


- Slide 1 - 

Welcome to the second unit of our MongoDB course!  In this module, we will dive deeper into advanced topics and concepts that will further enhance your understanding and proficiency in working with MongoDB. 


- Slide 2 - 

In this particular lesson, we will focus on the following objectives:

1. You will learn how to set up and manage the MongoDB service on both macOS and Windows operating systems. We will cover the installation process, configuring the service, and starting and stopping the  server.

2. We will explore MongoDB Compass, a powerful graphical user interface tool that provides a user-friendly way to interact with it. You will learn how to navigate the interface, connect to the databases, and perform various operations such as creating databases, managing collections, and manipulating documents.

3. We will also introduce the MongoDB Shell, a command-line interface that allows you to execute commands and queries directly against the server. You will gain hands-on experience using the shell to interact with databases, collections, and documents, and learn essential commands for data manipulation and querying.

4. Throughout the course, we will explore the fundamental aspects of managing databases, collections, and documents. You will learn how to create and drop databases, design efficient collections, insert and retrieve documents, update and delete data, and perform advanced queries using MongoDB's powerful querying capabilities.

By the end of this course, you will have a comprehensive understanding of running the MongoDB service on macOS and Windows, utilizing MongoDB Compass for graphical management, utilizing MongoDB Shell for command-line operations, and effectively managing databases, collections, and documents.



- Slide 3 - 

To manage services on macOS, you can use the following commands:

To start the service, open the terminal and run the command: `brew services start mongodb-community@4.4`. This will initiate the MongoDB service and make it available for use.

If you need to stop the service, execute the command: `brew services stop mongodb-community@4.4`. This will stop the service and terminate its processes.

To restart the MongoDB service, simply run the command: `brew services restart mongodb-community@4.4`. This will stop and then start the service, ensuring a fresh instance is running.

To view a list of all services managed by Homebrew, use the command: `brew services list`. This will provide the information about the running status of the MongoDB service.

Please note that the provided commands assume you have MongoDB installed using Homebrew and that the MongoDB service is managed by Homebrew services. Adjust the version number in the commands to match your installed MongoDB version.


- Slide 4 - 

To manage MongoDB services on Windows, you can use the following commands in the Command Prompt with administrative privileges:

To start the service, run the command `net start MongoDB`. 

For stopping the service, use `net stop MongoDB`. 

If you want to restart the MongoDB service, you can enter `net stop MongoDB && net start MongoDB`. 

To list the services and obtain service information, execute the command `sc query MongoDB`.

Please note that these commands assume MongoDB is installed as a Windows service. Adjust the command if your MongoDB service has a different name or if you have multiple MongoDB services installed. Ensure you run the Command Prompt as an administrator to have the necessary privileges for managing the services.




- Slide 5 - 

Next, I'd like to introduce you to MongoDB Compass, an intuitive graphical user interface designed for managing MongoDB databases. With MongoDB Compass, you can easily navigate, analyze, and interact with your data in a visually appealing and user-friendly manner.


One of the key features of MongoDB Compass is its ability to provide a comprehensive overview of your databases, collections, and documents. You can effortlessly explore the structure of your databases and collections, gaining insights into the relationships and organization of your data.


Using MongoDB Compass, you can perform various operations on your databases and collections with just a few clicks. You can create new databases and collections, modify existing ones, and manage indexes to optimize query performance. The user-friendly interface makes it simple to perform common tasks like inserting, updating, and deleting documents.


Additionally, MongoDB Compass offers advanced querying capabilities. You can construct complex queries using a visual query builder or write custom queries using MongoDB's powerful query language. The results are displayed in a clear and organized manner, allowing you to analyze and interpret your data effectively.


Furthermore, MongoDB Compass provides visualization tools that help you gain deeper insights into your data. You can create charts, graphs, and maps based on your MongoDB collections, allowing you to visualize trends, patterns, and geographical data.


Without a doubt, it's an indispensable tool for managing and exploring your MongoDB databases. Its user-friendly interface, powerful querying capabilities, and visualization tools make it easier for developers to work with MongoDB data. Whether you're navigating databases, collections, or documents, MongoDB Compass provides a seamless experience that enhances your productivity and understanding of your data.




- Slide 6 - 

The MongoDB Shell is a powerful command-line interface that provides developers, administrators, and data analysts with direct access to MongoDB's functionality. With the MongoDB Shell, you can execute commands, run queries, and perform administrative tasks, all from the command line. This versatile tool allows you to interact with your databases and collections efficiently and effectively. Whether you need to create, update, or delete documents, manage indexes, or perform complex aggregations, the MongoDB Shell provides a seamless and intuitive environment for executing these tasks. Its command-line interface offers flexibility and automation, making it an essential tool. With the MongoDB Shell, you have direct control and visibility into your MongoDB database operations, empowering you to manage and manipulate your data with ease.


- Slide 7 - 

Next, we will have a walkthrough on using MongoDB tools to create, modify, and delete databases, collections, and documents while emphasizing the importance of proper database management:

1. Start by launching the MongoDB Shell, depending on your preferred interface. This will provide you with a graphical or command-line interface to interact with MongoDB.

2. Creating a Database:
   - In the MongoDB Shell, use the command `use <database_name>` to switch to a specific database or select the database from the MongoDB Compass interface.
   - To create a new database, execute the command `db.createCollection("<collection_name>")` in the MongoDB Shell or use the GUI option available in MongoDB Compass.

3. Modifying a Database:
   - To modify a database, use various commands available in the MongoDB Shell or the GUI options in MongoDB Compass. For example, you can insert a new document using `db.<collection_name>.insertOne(<document>)`, update an existing document using `db.<collection_name>.updateOne(<filter>, <update>)`, or delete a document using `db.<collection_name>.deleteOne(<filter>)`.

4. Creating and Modifying Collections:
   - In MongoDB Compass, navigate to the selected database and use the GUI options to create a new collection or modify an existing one.
   - In the MongoDB Shell, use the command `db.createCollection("<collection_name>")` to create a new collection within the selected database.

5. Deleting Databases and Collections:
   - In MongoDB Compass, select the database or collection you want to delete and use the GUI options to delete it.
   - In the MongoDB Shell, use the command `db.<collection_name>.drop()` to delete a collection, and the command `db.dropDatabase()` to delete an entire database.
   
6. Proper Database Management:

- Regularly review and optimize indexes to improve query performance.
- Implement data backups and disaster recovery plans to safeguard against data loss.
- Use access control mechanisms to secure the database and limit user privileges.
- Consider data modeling techniques to create efficient and maintainable database schemas.
- Monitor database performance and usage to identify bottlenecks and optimize resource utilization.


- Hands on -

We'll move away a bit from our slides so that I can introducue you to another tool which is MongoDB Compass. MongoDB Compass allows us to interact with MongoDB databases. It's a powerful tool that allows for visiual exploration and managment of our data  while simplifying many administragtive tasks.

For the most part, in the future, when working with mongoDB we will often be working directly from the Shell, which we will explore further next. That said, for learning purposes, and for visualization of our data, the Compass tool is very helpful since it allows us to see all of our databases, collections and documents. From the Compass tool, we are also able to add new documents, update existing document and delete them as well. Therefor, I'd like to take a moment to introduce you to the tool, how it is we will get it up and running with a database and how to interact with that data 

***Compass***

1. Head to Compass and find the welcome screen with an input for the connection string, which is a special MongoDB URL for connecting to a MongoDB cluster.

2. Click on the "Connect" option without adding a connection string to connect to the local MongoDB. Make sure the MongoDB service is running if the connection doesn't work.

3. After connecting, view the available databases, which may include pre-made ones like the "local" database containing startup log data. Click on a database to see its collections and documents.

4. To add a new database, click the "+" sign above the database list, provide a name (e.g., "bookstore"), and create collections within the database for different types of data (e.g., books, authors, customers).

5. To add data to a collection, select it and click "Add Data" > "Insert Documents." MongoDB will generate an automatic ID for each document (record) in the collection. You can edit the data in JSON-like format using curly brackets.

```JSON
{
"title": "The Day that Changed Everything",
"author": "Catherine Miller", 
"pages": 500,
"genres": ["Fiction", "Romance novel"],
"rating": 9
}
```

Let's add the following document:

```JSON
[
{
"title": "It Ends With Us",
"author": "Colleen Hoover", 
"pages": 460,
"genres": ["Fiction", "Romance novel"],
"rating": 8
},

{
"title": "A Game of Gods",
"author": "Scarlett St. Clair", 
"pages": 247,
"genres": ["Fairy tale", "Romance fantasy", "Erotic literature"],
"rating": 5
},

{
"title": "If You Tell",
"author": "Gregg Olsen", 
"pages": 473,
"genres": ["True crime", "Biograpy"],
"rating": 9
},
{
"title": "The Six",
"author": "Anni Taylor", 
"pages": 746,
"genres": ["Historical Fiction"],
"rating": 6
}
]
```

Notice that if we hover over a document, we see the icons on the right which allows us to delete, edit, and we can also filter the data we see here. Let's assume we want to filter the data by rating:

```JSON
{rating: 9}
```

But we'll explore filtering in more detail in a later lesson. 

Finally, if we want to delete a database or collection we simply click on the options associated with it and select the bin or the drop collection option. 

So this is the basics of Compass which we will be using to visualize our data as we go on. 



## Running MongoDB service for macOS and Windows

Here are the instructions for starting and stopping the MongoDB service on both macOS and Windows operating systems:

####  Service on macOS:
To start, stop, restart, and list MongoDB services on macOS, you can use the following commands:

1. Start MongoDB service:
   ```
   brew services start mongodb-community@4.4
   ```

2. Stop MongoDB service:
   ```
   brew services stop mongodb-community@4.4
   ```

3. Restart MongoDB service:
   ```
   brew services restart mongodb-community@4.4
   ```

4. List MongoDB services:
   ```
   brew services list
   ```

The above commands assume that you have MongoDB installed using Homebrew and the MongoDB service is managed by Homebrew services. The version specified in the commands is 4.4, but you can replace it with your installed MongoDB version if different.


#### Service on Windows:
To start, stop, restart, and list MongoDB services on Windows, you can use the following commands:

1. Start MongoDB service:
   Open the Command Prompt as an administrator and run the command:
   ```
   net start MongoDB
   ```

2. Stop MongoDB service:
   Open the Command Prompt as an administrator and execute the command:
   ```
   net stop MongoDB
   ```

3. Restart MongoDB service:
   Open the Command Prompt as an administrator and enter the command:
   ```
   net stop MongoDB && net start MongoDB
   ```

4. List MongoDB services:
   Open the Command Prompt as an administrator and use the command:
   ```
   sc query MongoDB
   ```

These commands assume that you have MongoDB installed as a Windows service. The "net start" command starts the MongoDB service, "net stop" stops the MongoDB service, and "sc query" lists the MongoDB service information.

Please note that you might need to adjust the command if your MongoDB service has a different name or if you have multiple MongoDB services installed.



## MongoDB Compass (GUI tool)

MongoDB Compass is a powerful graphical user interface (GUI) that provides an intuitive and user-friendly way to manage MongoDB databases. It offers a comprehensive set of tools and features to navigate, analyze, and interact with your MongoDB data. Let's explore some key features of MongoDB Compass:

1. Visual Database Navigation:
MongoDB Compass allows you to easily navigate through databases, collections, and documents. It provides a visual representation of your data hierarchy, making it simple to browse and locate specific data points within your MongoDB environment.

2. Schema Exploration:
With MongoDB Compass, you can explore the schema of your collections and gain insights into the structure of your data. It provides an overview of the fields and their data types, allowing you to understand the data model and make informed decisions when querying and manipulating your data.

3. Query Building:
MongoDB Compass includes a built-in query builder that enables you to construct complex queries without writing any code. You can visually define query filters, projections, sorting, and aggregation stages using an intuitive interface. This feature simplifies the process of querying and retrieving the desired data from your MongoDB databases.

4. Document Editing and Creation:
Using MongoDB Compass, you can edit existing documents and create new ones directly within the GUI. It provides a user-friendly editor where you can modify field values, add new fields, or remove existing ones. This feature streamlines the process of updating and managing your MongoDB documents.

5. Aggregation Pipeline Visualization:
The Aggregation Pipeline feature in MongoDB Compass allows you to visually design, test, and analyze your aggregation pipelines. You can interactively build and modify the stages of the pipeline, observe the intermediate results, and optimize the pipeline for efficient data processing and analysis.

6. Performance Monitoring:
MongoDB Compass offers performance monitoring capabilities to track the performance of your MongoDB server and identify potential bottlenecks. You can view real-time metrics, query performance statistics, and gain insights into the health and efficiency of your database operations.

MongoDB Compass provides a comprehensive GUI that simplifies database management and enhances productivity when working with MongoDB. Its intuitive interface, powerful querying capabilities, document editing functionality, and visualization tools make it an essential tool for developers, database administrators, and anyone working with MongoDB databases.



## MongoDB Shell (GUI tool)

The MongoDB Shell is a versatile and powerful command-line interface (CLI) that provides a direct and efficient way to interact with MongoDB. It offers a range of features and functionalities for executing commands, queries, and administrative tasks. Let's explore some key aspects of the MongoDB Shell:

1. Interactive JavaScript Environment:
The MongoDB Shell provides an interactive JavaScript environment, allowing you to execute JavaScript code directly in the shell. This enables you to perform complex data manipulations, write custom scripts, and leverage the full power of JavaScript for MongoDB operations.

2. Command Execution:
With the MongoDB Shell, you can execute a wide range of commands to manage databases, collections, documents, and indexes. It supports various administrative commands, CRUD operations, aggregation pipelines, and more. You can easily switch between different databases and perform administrative tasks efficiently.

3. Querying and Aggregation:
The MongoDB Shell allows you to execute queries and aggregation pipelines to retrieve and process data. You can write queries using the MongoDB Query Language (MQL) and perform advanced data aggregations using the Aggregation Framework. This flexibility empowers you to retrieve, filter, and transform data according to your specific requirements.

4. Database Administration:
The MongoDB Shell provides administrative capabilities for managing databases and collections. You can create and drop databases, create and modify collections, manage indexes, and perform backup and restore operations. These administrative tasks can be accomplished efficiently using the MongoDB Shell.

5. Scripting and Automation:
The MongoDB Shell is scriptable, allowing you to write scripts and automate repetitive tasks. You can create scripts to perform data migrations, database provisioning, data imports, and more. The ability to script and automate tasks using the MongoDB Shell enhances productivity and enables efficient management of MongoDB deployments.

6. Diagnostic and Debugging Tools:
The MongoDB Shell offers built-in diagnostic and debugging tools to aid in troubleshooting and performance optimization. You can access detailed logs, monitor server statistics, analyze query performance, and diagnose issues directly from the shell. This helps in maintaining the health and efficiency of your MongoDB environment.

The MongoDB Shell serves as a powerful and flexible command-line interface for executing commands, queries, and administrative tasks in MongoDB. Its interactive JavaScript environment, extensive command support, querying and aggregation capabilities, database administration features, scripting and automation capabilities, and diagnostic tools make it an essential tool for developers, database administrators, and anyone working with MongoDB deployments.

## Managing databases, collections, and documents


 Next, we have a walkthrough on using MongoDB tools to create, modify, and delete databases, collections, and documents while emphasizing the importance of proper database management:

1. Start by launching the MongoDB Shell or MongoDB Compass, depending on your preferred interface.

2. Creating a Database:

- Use the command `use <database_name>` in the MongoDB Shell to switch to a specific database or select the database from the MongoDB Compass interface.
- To create a new database, execute the command `db.createCollection("<collection_name>")` in the MongoDB Shell or use the GUI option in MongoDB Compass.

3. Modifying a Database:

- To modify a database, you can use commands like `db.<collection_name>.insertOne(<document>)` to insert a new document,` db.<collection_name>.updateOne(<filter>, <update>)` to update an existing document, or `db.<collection_name>.deleteOne(<filter>)` to delete a document.

4. Creating and Modifying Collections:

- In MongoDB Compass, navigate to the selected database and use the GUI options to create a new collection or modify an existing one.
- In the MongoDB Shell, use the `db.createCollection("<collection_name>")` command to create a new collection.

5. Deleting Databases and Collections:

- In MongoDB Compass, select the database or collection you want to delete and use the GUI options to delete it.
- In the MongoDB Shell, use the `db.<collection_name>.drop()` command to delete a collection, and the `db.dropDatabase()` command to delete a database.

6. Proper Database Management:
It is essential to follow best practices for database management to ensure data integrity, performance, and scalability.

- Regularly review and optimize indexes to improve query performance.
- Implement data backups and disaster recovery plans to safeguard against data loss.
- Use access control mechanisms to secure the database and limit user privileges.
- Consider data modeling techniques to create efficient and maintainable database schemas.
- Monitor database performance and usage to identify bottlenecks and optimize resource utilization.

Proper database management is crucial to ensure the reliability, security, and efficiency of your MongoDB deployments. By using the appropriate tools and following best practices, you can create, modify, and delete databases, collections, and documents effectively while maintaining the health of your MongoDB environment.


## Assessment

Here's a 10-question assessment based on the information provided:

1. What command is used to start the MongoDB service on macOS?
a) `brew services start mongodb-community@4.4`
b) `net start MongoDB`
c) `brew services stop mongodb-community@4.4`
d) `net stop MongoDB`

2. How can you stop the MongoDB service on Windows?
a) `brew services start mongodb-community@4.4`
b) `net start MongoDB`
c) `brew services stop mongodb-community@4.4`
d) `net stop MongoDB`

3. Which MongoDB tool provides a graphical user interface (GUI) for managing databases?
a) MongoDB Shell
b) MongoDB Compass
c) MongoDB Atlas
d) MongoDB Server

4. What is the purpose of MongoDB Compass?
a) To execute MongoDB commands
b) To perform data aggregations
c) To monitor database performance
d) To manage MongoDB databases through a GUI

5. Which feature of MongoDB Compass allows you to visually design and analyze aggregation pipelines?
a) Visual Database Navigation
b) Schema Exploration
c) Query Building
d) Aggregation Pipeline Visualization

6. What type of environment does the MongoDB Shell provide for executing commands?
a) Graphical user interface (GUI)
b) Command-line interface (CLI)
c) Web-based interface
d) Interactive JavaScript environment

7. Which command is used to create a new collection in MongoDB Shell?
a) `db.createCollection("<collection_name>")`
b) `db.insertOne(<document>)`
c) `db.drop()`
d) `db.dropDatabase()`

8. In MongoDB Compass, how can you delete a collection?
a) Using the `db.drop()` command
b) Selecting the collection and using GUI options
c) Using the `db.dropDatabase()` command
d) Using the `db.createCollection("<collection_name>")` command

9. What are some best practices for proper database management in MongoDB?
a) Regularly reviewing and optimizing indexes
b) Using random collection names
c) Disabling access control mechanisms
d) Ignoring database performance monitoring

10. Why is proper database management important in MongoDB?
a) It improves query performance
b) It enhances data security
c) It ensures data integrity
d) All of the above

Answers:
1. a) `brew services start mongodb-community@4.4`
2. d) `net stop MongoDB`
3. b) MongoDB Compass
4. d) To manage MongoDB databases through a GUI
5. d) Aggregation Pipeline Visualization
6. d) Interactive JavaScript environment
7. a) `db.createCollection("<collection_name>")`
8. b) Selecting the collection and using GUI options
9. a) Regularly reviewing and optimizing indexes
10. d) All of the above