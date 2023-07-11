# Module 1: Introduction to MongoDB


## Table of Contents
1. What is MongoDB
2. Advantages and use cases of MongoDB
3. Installation and setup



## Introduction


- Slide 1 -
Thank you for choosing Craft Knowledge's comprehensive MongoDB course. I'm Ana, your instructor for this course, and I'll guide you through all the essential concepts and operations of MongoDB.


As we start our journey, you will find that MongoDB is very versatile allowing it to be used in just about any project you may be working on including websites, mobile apps, and desktop apps. It's versatile because it is a fast and efficient way to store data without stressing over database configurations, setup, or structure.




- Slide 2 -
Throughout this MongoDB course, we will cover a range of important objectives. We will begin by exploring the fundamental question of "What is MongoDB?" This will provide us with a solid understanding of its purpose, features, and how it differs from other database management systems. We will then delve into the advantages and use cases of MongoDB, discovering the unique benefits it offers and the various scenarios in which it excels. Additionally, we will guide you through the installation and setup process, ensuring that you have a solid foundation to work with MongoDB effectively. By accomplishing these objectives, you will gain a comprehensive understanding of MongoDB, its strengths, and how to set it up for successful implementation in your projects.


- Slide 3 -


MongoDB is a widely adopted NoSQL document-oriented database management system. It offers a highly flexible and scalable solution for storing and accessing data. In contrast to traditional SQL databases, MongoDB adopts a distinct approach by utilizing flexible JSON-like documents instead of tables and rows. This allows for the seamless management of diverse and evolving data structures, enabling developers to efficiently work with data in a more intuitive and adaptable manner.




- Slide 4 -


MongoDB, a NoSQL database, offers several advantages over traditional SQL databases. Here are some of the key benefits of MongoDB:


1. Flexible document-based data model: MongoDB allows you to store data in flexible, schema-less JSON-like documents. This provides the ability to handle evolving data structures and easily accommodate changes in your application's requirements.


2. Scalability and high performance: MongoDB is designed to scale horizontally, allowing you to distribute data across multiple servers or clusters. This enables seamless scaling as your application grows, ensuring high performance and the ability to handle large amounts of data.


3. Rich indexing and querying capabilities: MongoDB supports indexing on any attribute within a document, enabling efficient querying and retrieval of data. It provides a powerful query language with a wide range of operators and functions, making it easy to work with data.


4. Replication and high availability: MongoDB provides built-in replication, allowing you to create replicas of your data across multiple servers. This ensures data redundancy, fault tolerance, and automatic failover, resulting in high availability of your database.


These features and advantages make MongoDB a powerful and flexible database solution for a wide range of applications including content management systems (CMD),s real-time analytic, and user data management




- Slide 5 -


MongoDB provides installation options for multiple operating systems, ensuring compatibility with Windows, macOS, and Linux. To begin the installation, users can access installation packages directly from the official MongoDB website. The setup process involves configuring the MongoDB server, specifying data directories for storage, and initiating the database service. By following these steps, users can successfully set up and start MongoDB, allowing them to harness the power of this versatile database management system on their preferred operating system.





## Setup Environment

We will begin my installing MongoDB community edition which is a third-party Homebrew package manager. The advange to this is that it also installs the MongodB datagase tools that we will be working with. 


### Installing MongoDB FOR MAC

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

   Note: For future reference, to stop the service you would run the followng command on the terminal: 
   ```
   brew services stop mongodb-community
   ```


6. To install the MongoDB command-line tools, run the following command:
   ```
   brew install mongodb-database-tools
   ```

   This will install a collection of MongoDB tools, including `mongodump`, `mongorestore`, `mongoexport`, `mongoimport`, and others.

That's it! MongoDB and its tools are now installed on your macOS using Homebrew. You can interact with MongoDB through the MongoDB shell using the `mongo` command, or use the various command-line tools for data management and analysis. Make sure to consult the official MongoDB documentation for further guidance on using MongoDB and its tools.

### Installing MongoDB for Windows







## Resources

* [MongoDB Community Dowloads](https://www.mongodb.com/try/download/community-kubernetes-operator)
* [MongoDB docs on macOS installation](https://www.mongodb.com/docs/manual/tutorial/install-mongodb-on-os-x/)
* [Homebrew installation for macOS](https://brew.sh/#install)

* []










