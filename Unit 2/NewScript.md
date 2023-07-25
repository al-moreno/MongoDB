- Slide 1 -


Welcome to the second unit of our MongoDB course! In this module, we will dive deeper into advanced topics and concepts that will further enhance your understanding and proficiency in working with MongoDB.




- Slide 2 -


In this particular lesson, we will focus on the following objectives:


1. You will learn how to set up and manage the MongoDB service on both macOS and Windows operating systems. We will cover the installation process, configuring the service, and starting and stopping the server.


2. We will explore MongoDB Compass, a powerful graphical user interface tool that provides a user-friendly way to interact with it. You will learn how to navigate the interface, connect to the databases, and perform various operations such as creating databases, managing collections, and manipulating documents.


3. We will also introduce the MongoDB Shell, a command-line interface that allows you to execute commands and queries directly against the server. You will gain hands-on experience using the shell to interact with databases, collections, and documents, and learn essential commands for data manipulation and querying.


4. Throughout the course, we will explore the fundamental aspects of managing databases, collections, and documents. You will learn how to create and drop databases, design efficient collections, insert and retrieve documents, update and delete data, and perform advanced queries using MongoDB's powerful querying capabilities.


By the end of this course, you will have a comprehensive understanding of running the MongoDB service on macOS and Windows, utilizing MongoDB Compass for graphical management, utilizing MongoDB Shell for command-line operations, and effectively managing databases, collections, and documents.






- Slide 3 -


To manage services on macOS, you can use the following commands:


To start the service, open the terminal and run the command: `brew services start mongodb-community@4.4`. This will initiate the MongoDB service and make it available for use.


If you need to stop the service, execute the command: `brew services stop mongodb-community@4.4`. This will stop the service and terminate its processes.


To restart the MongoDB service, simply run the command: `brew services restart mongodb-community@4.4`. This will stop and then start the service, ensuring a fresh instance is running.


To view a list of all services managed by Homebrew, use the command: `brew services list`. This will provide information about the running status of the MongoDB service.


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


MongoDB Compass is a user-friendly graphical interface offered by MongoDB for interacting with MongoDB databases. It caters to developers, database administrators, and users, simplifying data visualization and manipulation without extensive command-line expertise
Key features include:


1. Visual Database Navigation: MongoDB Compass offers an intuitive interface for easy navigation through databases, collections, and documents, simplifying data browsing and locating specific data points.


2. Schema Exploration: Compass allows users to explore collection schemas, gaining insights into data structure and types, and enabling informed decisions in data manipulation.


3. Query Building: The built-in query builder allows users to construct complex queries visually without coding, defining filters, projections, sorting, and aggregation stages effortlessly.


4. Document Editing and Creation: Users can directly edit and create MongoDB documents within the GUI, facilitating efficient data management.


5. Aggregation Pipeline Visualization: Compass enables users to visually design, test, and analyze aggregation pipelines, optimizing data processing and analysis.


6. Performance Monitoring: MongoDB Compass provides performance monitoring with real-time metrics, query statistics, and insights into database efficiency, facilitating performance optimization.


Overall, MongoDB Compass is a valuable tool for developers seeking a GUI for MongoDB tasks.








- Slide 7 -


The MongoDB Shell is a powerful command-line interface that provides developers, administrators, and data analysts with direct access to MongoDB's functionality. With the MongoDB Shell, you can execute commands, run queries, and perform administrative tasks, all from the command line. This versatile tool allows you to interact with your databases and collections efficiently and effectively. Whether you need to create, update, or delete documents, manage indexes, or perform complex aggregations, the MongoDB Shell provides a seamless and intuitive environment for executing these tasks. Its command-line interface offers flexibility and automation, making it an essential tool. With the MongoDB Shell, you have direct control and visibility into your MongoDB database operations, empowering you to manage and manipulate your data with ease.


- Slide 8 -


MongoDB facilitates managing data in a flexible and scalable manner. Databases are containers holding collections of related data. Collections group documents, which are JSON-like data units. MongoDB's schemaless nature allows easy adaptation to changing data requirements. CRUD operations (Create, Read, Update, Delete) are employed to manage data. On our current slide, we see a variety of queries that are executed using a flexible and expressive language. Indexing improves query performance. Aggregation pipelines enable complex data processing while allowing for horizontal scaling. It ensures data availability and reliability with replica sets and sharding.


We will be moving on shortly to our hands-on portion of this less where we will be implementing some of the commands for:
1. For creating a database:
- To create a new database: `db.createCollection("<collection_name>")`
- To switch to a specific database: `use <database_name>`
2. For modifying a database:
- Insert a new document: `db.<collection_name>.insertOne(<document>)`
- Update an existing document: `db.<collection_name>.updateOne(<filter>, <update>)`
- Delete a document : `db.<collection_name>.deleteOne(<filter>)`.


4. Creating and modifying collections: `db.createCollection("<collection_name>")`


5. Deleting databases and collections:
- Delete a collection: `db.<collection_name>.drop()`
- Delete a database: `db.dropDatabase()`






## Running MongoDB service for macOS and Windows


Here are the instructions for starting and stopping the MongoDB service on both macOS and Windows operating systems:


#### Service on macOS:
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


The commands assume that you have MongoDB installed using Homebrew and the MongoDB service is managed by Homebrew services. The version specified in the commands is 4.4, but you can replace it with your installed MongoDB version if different.


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




## MongoDB Shell


We'll be looking at MongoDB tools next as we start with how we should create, modify, and delete databases, collections, and documents in Shell:


1. Start by launching the MongoDB Shell, depending on your preferred interface. This will provide you with a graphical or command-line interface to interact with MongoDB.


### Shell for MacOS


To launch the MongoDB shell on macOS, follow these steps:


1. Open the Terminal application on your macOS. You can find it in the "Utilities" folder within the "Applications" folder, or you can use Spotlight search (Cmd + Space) and type "Terminal" to find it.


2. Once the Terminal is open, type the following command to launch the MongoDB shell:


```
mongo
```


3. Press Enter, and the MongoDB shell should start. It will connect to the default MongoDB instance running on your local machine.


That's it! You should now see the MongoDB shell prompt, which looks like this:


```
MongoDB shell version: x.x.x
connecting to: test
>
```


Replace "x.x.x" with the version number of the MongoDB shell installed on your machine. Now you can interact with your MongoDB instance using various commands in the shell.






### Shell for Windows




To launch the MongoDB shell on Windows, follow these steps:


1. Open the Command Prompt or PowerShell on your Windows machine. You can do this by searching for "cmd" or "PowerShell" in the Start menu or using the "Run" dialog (Win + R).


2. Navigate to the MongoDB installation directory. By default, MongoDB is installed in the "C:\Program Files\MongoDB\Server\{version}\bin" folder. Replace "{version}" with the specific version number installed on your system.


3. Once you are in the "bin" directory, type the following command to launch the MongoDB shell:


For Command Prompt:
```
mongo
```


For PowerShell:
```
.\mongo
```


4. Press Enter, and the MongoDB shell should start. It will connect to the default MongoDB instance running on your local machine.


You should now see the MongoDB shell prompt, which looks like this:


```
MongoDB shell version: x.x.x
connecting to: test
>
```


Replace "x.x.x" with the version number of the MongoDB shell installed on your machine. Now you can interact with your MongoDB instance using various commands in the shell.




***MongoDB Shell for all***


Now all together we implement the following commands to perform the indicated actions:




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






## MongoDB Compass


MongoDB Compass allows us to interact with MongoDB databases. It's a powerful tool that allows for visual exploration and management of our data while simplifying many administrative tasks.


For the most part, in the future, when working with MongoDB we will often be working directly from the Shell, which we will explore further next. That said, for learning purposes, and for visualization of our data, the Compass tool is very helpful since it allows us to see all of our databases, collections, and documents. From the Compass tool, we are also able to add new documents, update existing documents and delete them as well. Therefore, I'd like to take a moment to introduce you to the tool, how it is we will get it up and running with a database, and how to interact with that data


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







