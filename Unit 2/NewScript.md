 
- Slide 1 -

Welcome to the second lesson of our MongoDB course! In this module, we will dive deeper into advanced topics and concepts that will further enhance our understanding and proficiency in working with MongoDB.

- Slide 2 -

In this particular lesson, we will focus on the following objectives:

1. You will learn how to run the MongoDB service on both macOS and Windows operating systems where we will learn how to start and stop the server.

2. We will explore MongoDB Compass, a powerful graphical user interface tool that provides a user-friendly way to interact with it. You will learn how to navigate the interface, connect to the databases, and perform various operations such as creating databases, managing collections, and manipulating documents.

3. We will also introduce the MongoDB Shell, a command-line interface that allows you to execute commands and queries directly against the server. You will gain hands-on experience using the shell to interact with databases, collections, and documents, and learn essential commands for data manipulation and querying.

4. Throughout the course, we will explore the fundamental aspects of managing databases, collections, and documents. You will learn how to create and drop databases, design efficient collections, insert and retrieve documents, update and delete data, and perform advanced queries using MongoDB's powerful querying capabilities.

By the end of this lesson, you will have a comprehensive understanding of running the MongoDB service on macOS and Windows, utilizing MongoDB Compass for graphical management, utilizing MongoDB Shell for command-line operations, and effectively managing databases, collections, and documents.


- Slide 3 -

To manage services on macOS, you can use the following commands:

- Start the service: `brew services start mongodb-community@4.4`. This will initiate the MongoDB service and make it available for use.

- Stop the service: `brew services stop mongodb-community@4.4`. This will stop the service and terminate its processes.

- Restart the service: `brew services restart mongodb-community@4.4`. This will stop and then start the service, ensuring a fresh instance is running.

- List all services managed by Homebrew: `brew services list`. This will provide information about the running status of the MongoDB service.

Please note that the commands assume you have MongoDB installed using Homebrew and that the MongoDB service is managed by Homebrew services. Adjust the version number in the commands to match your installed MongoDB version.



- Slide 4 -

To manage MongoDB services on Windows, you can use the following commands in the Command Prompt with administrative privileges:

- Start the service: `net start MongoDB`

- Stop the service: `net stop MongoDB`

- Restart the service: `net stop MongoDB && net start MongoDB`

- List all services: `sc query MongoDB`

Please note that these commands assume MongoDB is installed as a Windows service. Adjust the command if your MongoDB service has a different name or if you have multiple MongoDB services installed. Ensure you run the Command Prompt as an administrator to have the necessary privileges for managing the services.

- Slide 5 -

Next, I'd like to introduce you to MongoDB Compass, a graphical user interface designed for managing MongoDB databases. With Compass, you can easily navigate, analyze, and interact with your data in a visually appealing and user-friendly manner.

One of the key features of MongoDB Compass is its ability to provide a comprehensive overview of your databases, collections, and documents. You can effortlessly explore the structure of your databases and collections, gaining insights into the relationships and organization of your data.

Using Compass, you can perform various operations on your databases and collections with just a few clicks. You can create new databases and collections, modify existing ones, and manage indexes to optimize query performance. The user-friendly interface makes it simple to perform common tasks like inserting, updating, and deleting documents.

Additionally, Compass provides visualization tools that help you gain deeper insights into your data. You can create charts, graphs, and maps based on your MongoDB collections, allowing you to visualize trends, patterns, and geographical data.

MongoDB Compass is a great tool for managing and exploring your MongoDB databases. Its user-friendly interface, powerful querying capabilities, and visualization tools make it easier for developers to work with MongoDB data. Whether you're navigating databases, collections, or documents, MongoDB Compass provides a seamless experience that improves your productivity and understanding of your data.


- Slide 6 -

The MongoDB Shell is a powerful command-line interface that provides developers, administrators, and data analysts with direct access to MongoDB's functionality. With the MongoDB Shell, you can execute commands, run queries, and perform administrative tasks, all from the command line. This tool allows you to interact with your databases and collections efficiently and effectively. Whether you need to create, update, or delete documents, manage indexes, or perform complex aggregations, the MongoDB Shell provides a seamless and intuitive environment for executing these tasks. Its command-line interface offers flexibility and automation, making it an essential tool. With the MongoDB Shell, you have direct control and visibility into your database operations, allowing you to manage and manipulate your data with ease.


- Slide 8 -

MongoDB simplifies managing data in a flexible and scalable manner. Databases are containers holding collections of related data. Collections group documents, which are JSON-like data units. MongoDB's schemaless nature allows easy adaptation to changing data requirements. CRUD operations (Create, Read, Update, Delete) are employed to manage data. Currently, on the screen, we see a variety of queries that are executed using flexible and expressive language. Indexing improves query performance. Aggregation pipelines enable complex data processing while allowing for horizontal scaling. It ensures data availability and reliability with replica sets and sharding.

Shortly, we will move onto the hands-on portion of this lesson where we will be implementing some of the commands displayed here:
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
"title": "God Emperor of Dune",
"author": "Frank Herbert",
"pages": 340,
"genres": ["Sci-fi", "Novel"],
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
},
{
"title": "The White Plague",
"author": "Frank Herbert",
"pages": 343,
"genres": ["Sci-fi", "Novel"],
"rating": 9
},
]
```

Notice that if we hover over a document, we see the icons on the right which allows us to delete, edit, and we can also filter the data we see here. Let's assume we want to filter the data by rating:

```JSON
{rating: 9}
```

But we'll explore filtering in more detail in a later lesson.

Finally, if we want to delete a database or collection we simply click on the options associated with it and select the bin or the drop collection option.

So this is the basics of Compass which we will be using to visualize our data as we go on.



## MongoDB Shell

We'll be looking at MongoDB tools next as we start with how we should create, modify, and delete databases, collections, and documents in Shell:

1. Start by launching the MongoDB Shell. This will provide you with a command-line interface to interact with MongoDB.
- In Windows: `mongosh`
- In macOS: `mongo`
- In Compass: Direct


2. To create a new database I would simply have to switch to the non-existing database and add collections, MongoDB will create that database for us.


3. Display all databases: `show dbs`


4. Switch to a database: `use bookstore`


5. To Clear the screen: `cls`


6. See the current database we are in: `db`


7. List all collections in the current database: `show `


7. To see collections in the current database: `show collections`


8. We can also create variables: `var userName = "Michelangelo"`. and if we enter the command: `userName` we get back the value of that variable. We can change it to `userName = "Leonardo"` and I can say `userName` again and we get the updated variable value.


9. Currently, looking on Compass we see the database of the bookstore and inside there is a books collection. Inside the books collection, we see a few documents. We added those documents in the previous lesson. Next, I'd like to show you how we add documents to a collection from the Shell. We'll begin by first making sure we are in the bookstore database (`use bookstore`). Once in the bookstore database, we'll need to reference a collection (`db.books`). Next we append a method `inserOne()`. This function will insert a single document where we pass an argument:

```JSON
db.books.insertOne({
title: "The Nurse's Secret",
author: "Amanda Skenandore",
pages: 300,
rating: 7,
genres:["Historical fiction", "Medical fiction"]
})
```
Looking back at Compass we now see our new document in the books collection.

By the way, you don't need a collection to exist for you to add a document. MongoDB will automatically add it for you to insert a document.
```JSON
db.authors.insertOne({
name: "Amanda Skenandore",
age: 33,
})
```

We can also insert many documents at once by using a different method:
```JSON
db.books.insertMany([
{
title: "The Light Fantastic",
author: "Terry Pratchett",
pages: 250,
rating: 6,
genres: ["Fantasy"]
},
{
title: "Dune",
author: "Frank Herbert",
pages: 500,
rating: 10,
genres: ["Sci-fi", "Novel", "Adventure fiction"]
}
])

```


10. We've seen how to add documents, now we want to see how we can update documents and we can do that by using one of two methods: `updateOne()` or `updateMany()`.

***Update one***
- First, we'll want to see all the documents we have by using the `db.books.find()`.
- Say I want to update the number of pages and rating in a specific book. We'll do so by using the Object ID: `db.collection.updateOne()` and it takes two arguments, the first is what we want to update and the second will specify the fields we want to update, we do so with a `$set` operator
```JSON
db.books.updateOne(
{
_id: <objectID>
},
{
$set: {rating: 7,
pages: 260}
}
)
```
- Well now want to verify by saying `db.books.find()`


***Update Many***
- What if we want to update many documents at once? Well start with looking for the documents we want to update by running: `db.books.find()`
- Say we've misspelled an author's name and we need to change all the books for that author to have the correct spelling. We can use the `updateMany()` method where we provide two arguments, the first to tell MongoDB what we want to update and the second to tell it what we want the change to be:
```JSON
db.books.updateMany(
{
author: "Frank Herbert"
},
{$set: {author: "Frank Herbertt" }}
)
```
- We'll confirm: `db.books.find()`

11. The next thing we'll look at is how we go about deleting a part of a collection but before, to avoid having to type everything again or to serve as a backup in case we make a mistake we'll want to export the data. Going to Compass, we click on the option that says `Export Full Collection`. Once we have that data we can proceed with deleting data. Similar to adding documents we have to methods available, we have `deleteOne()` and `deleteMany()`

- 1st we’ll start by saying: `db.books.find()` so that we can see all the books documents in the collection. I'll then copy the Object ID of one since I will be deleting the document with the ID. We want to then enter `db.books.deleteOne({_id:<paste id>})`. We use the ID because it's unique to this document.
- we then want to confirm that it is gone: `db.books.find()`

- To delete many documents: `db.books.deleteMany({author: "Frank Herbert"})`.
- we then want to confirm that it is gone: `db.books.find()`


5. Deleting Databases and Collections:
- In the MongoDB Shell, use the command `db.<collection_name>.drop()` to delete a collection,
- To delete a database entirely: `db.dropDatabase()`





