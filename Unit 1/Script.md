# Module 1: Introduction to MongoDB


## Table of Contents
1. What is MongoDB
2. Advantages and use cases of MongoDB
3. Installation and setup
4. Assessment
5. Resources



## Introduction


- Slide 1 

Thank you for choosing Craft Knowledge's comprehensive MongoDB course. I'm Ana, your instructor for this course, and I'll guide you through all the essential concepts and operations of MongoDB.


As we start our journey, you will find that MongoDB is very versatile allowing it to be used in just about any project you may be working on including websites, mobile apps, and desktop apps. It's versatile because it is a fast and efficient way to store data without stressing over database configurations, setup, or structure.




- Slide 2 

Throughout this course, we will cover a range of important objectives. We will begin by exploring the fundamental question of "What is MongoDB?" This will provide us with a solid understanding of its purpose, features, and how it differs from other database management systems. We will then delve into the advantages and use cases of MongoDB, discovering the unique benefits it offers and the various scenarios in which it excels. Additionally, we will guide you through the installation and setup process, ensuring that you have a solid foundation to work with it effectively. By accomplishing these objectives, you will gain a comprehensive understanding of MongoDB, its strengths, and how to set it up for successful implementation in your projects.


- Slide 3 


MongoDB is a widely adopted NoSQL document-oriented database management system. It offers a highly flexible and scalable solution for storing and accessing data. In contrast to traditional SQL databases, MongoDB adopts a distinct approach by utilizing flexible JSON-like documents instead of tables and rows. This allows for the seamless management of diverse and evolving data structures, enabling developers to efficiently work with data in a more intuitive and adaptable manner.




- Slide 4 


As a NoSQL database, it offers several advantages over traditional SQL databases. Here are some of the key benefits of MongoDB:


1. (Flexible document-based data model: ) MongoDB allows you to store data in flexible, schema-less JSON-like documents. This provides the ability to handle evolving data structures and easily accommodate changes in your application's requirements.


2.( Scalability and high performance:) What's more, it' is designed to scale horizontally, allowing you to distribute data across multiple servers or clusters. This enables seamless scaling as your application grows, ensuring high performance and the ability to handle large amounts of data.


3. (Rich indexing and querying capabilities:) Additionally, It supports indexing on any attribute within a document, enabling efficient querying and retrieval of data. It provides a powerful query language with a wide range of operators and functions, making it easy to work with data.


4.( Replication and high availability: ) Finally, it provides built-in replication, allowing you to create copies of your data across multiple servers. This ensures data redundancy, fault tolerance, and automatic failover, resulting in high availability of your database.


- slide 5 

These features and advantages make MongoDB a powerful and flexible database solution for a wide range of applications including content management systems, real-time analitics and reporting, and user data management




- Slide 6 


Finally, m`ongoDB provides installation options for multiple operating systems, ensuring compatibility with Windows, macOS, and Linux. To begin the installation, users can access installation packages directly from the official MongoDB website. The setup process involves configuring the MongoDB server, specifying data directories for storage, and initiating the database service. By following these steps, users can successfully set up and start MongoDB, allowing them to harness the power of this versatile database management system on their preferred operating system.





## Setup Environment of MongoDB for macOS


We will begin by installing MongoDB community edition which is a third-party Homebrew package manager. The advantage to this is that it also installs the MongoDB database tools that we will be working with.


To install MongoDB and its tools on macOS using Homebrew, follow these steps:


1. Open the Terminal application on your macOS.


2. Install Homebrew if you haven't already by running the following command and following the prompts:
```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```
After running the command, you need to press Enter to start the installation process of Homebrew on your macOS system.


The command initiates the installation script for Homebrew. It uses the curl command to download the script from the specified URL, and the bash command executes the script. The script will guide you through the installation process and prompt you for your password, as it requires administrative privileges to install Homebrew.


Once you enter your password and press Enter, the installation script will continue to set up Homebrew on your macOS system. It will download and install the necessary files and dependencies to enable you to use Homebrew for package management.


Once the installation is complete, you will see a message indicating that Homebrew has been successfully installed. You can then proceed with installing MongoDB or any other packages using Homebrew.


3. Once Homebrew is installed, run the following command to tap into the MongoDB Homebrew Tap:
```
brew tap mongodb/brew
```


4. To install MongoDB, use the following command:
```
brew install mongodb-community
```


5. After the installation is complete, you can start the MongoDB service by running the following command:
```
brew services start mongodb-community
```


This will start the MongoDB server in the background. You can verify that MongoDB is running by executing the command `brew services list`, which will display the running services, including MongoDB.


Note: For future reference, to stop the service you would run the following command on the terminal:
```
brew services stop mongodb-community
```




6. To install the MongoDB command-line tools, run the following command:
```
brew install mongodb-database-tools
```


This will install a collection of MongoDB tools, including `mongodump`, `mongorestore`, `mongoexport`, `mongoimport`, and others.


That's it! MongoDB and its tools are now installed on your macOS using Homebrew. You can interact with MongoDB through the MongoDB shell using the `mongo` command, or use the various command-line tools for data management and analysis. Consult the official MongoDB documentation for further guidance on using MongoDB and its tools.

## Setup Environment of MongoDB for Windows


The installation process of MongoDB on a Windows device is notably easier, thanks to the user-friendly installation wizard.


To install MongoDB and its tools on Windows, follow these steps:


1. Visit the MongoDB download page at https://www.mongodb.com/try/download/community and select your preferred Windows version.


2. Download the MongoDB Community Edition installer appropriate for your Windows version (e.g., MSI for Windows 64-bit).


3. Once the download is complete, open the installer package (.msi file) and follow the installation wizard.


4. In the installation wizard, choose the "Complete" setup type to install both the MongoDB server and the MongoDB tools.


5. Specify the installation directory where MongoDB will be installed. By default, it is installed in `C:\Program Files\MongoDB\Server\<version>`.


6. Configure the MongoDB server as a Windows service by selecting the "Run the service as Network Service user" option. This allows the MongoDB service to start automatically when Windows starts.


7. Click the "Install" button to start the installation process.


8. Once the installation is complete, MongoDB is ready to use. You can access MongoDB from the command line by opening a new Command Prompt window and running the `mongo` command.


9. Additionally, you can use MongoDB Compass, a graphical user interface tool, to interact with MongoDB. You can download MongoDB Compass from the MongoDB download page and install it on your Windows system.


That's it! MongoDB and its tools are now installed on your Windows machine. You can start using MongoDB by running the `mongo` command in the Command Prompt or by launching MongoDB Compass. Remember to refer to the MongoDB documentation for further instructions on using MongoDB and its various tools effectively.






## Assessment

Here's a 5-question assessment based on the content:

1. Which types of projects can MongoDB be used for?
a) Websites
b) Mobile apps
c) Desktop apps
d) All of the above

2. What is the key advantage of MongoDB's document-based data model?
a) Flexibility for handling evolving data structures
b) Superior scalability compared to SQL databases
c) Rich indexing and querying capabilities
d) Built-in replication for high availability

3. What are the benefits of MongoDB's scalability and high performance?
a) Efficient querying and retrieval of data
b) Ability to distribute data across multiple servers or clusters
c) Automatic failover and data redundancy
d) All of the above

4. Which operating systems are compatible with MongoDB?
a) Windows only
b) macOS only
c) Linux only
d) Windows, macOS, and Linux

5. What are the steps involved in installing MongoDB?
a) Download installation packages from the MongoDB website
b) Configure the MongoDB server and specify data directories
c) Start the database service
d) All of the above

Answers:
1. d) All of the above
2. a) Flexibility for handling evolving data structures
3. d) All of the above
4. d) Windows, macOS, and Linux
5. d) All of the above

## Resources

* [MongoDB Community Dowloads](https://www.mongodb.com/try/download/community-kubernetes-operator)
* [MongoDB docs on macOS installation](https://www.mongodb.com/docs/manual/tutorial/install-mongodb-on-os-x/)
* [Homebrew installation for macOS](https://brew.sh/#install)
* [MongoDB Community Dowload for Windows](https://www.mongodb.com/try/download/community)










