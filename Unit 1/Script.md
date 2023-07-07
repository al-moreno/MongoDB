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

Before we start to work with MongoDB, we first need a MongoDB database to work with. And there are a couple of options for setting up a database, we can use a hosted service like MongoDB Atlas and connect to that or we can install it locally onto our computer which is what we will be doing for this course to start

<!-- but later in the course, I will also show you how to set up a hosted database using MongoDB Atlas. -->


### Installing MongoDB

Let's begin by heading over to the [MongoDB website](https://www.mongodb.com/try/download/community) where we will select downloading the Free Community Server. Scrolling to about mid-page, where we can select the version, the platform, and the package type desired. Once we have done that we will select download.


#### FOR MAC

***Recommended***
Follow the instructions:
[MongoDB Install on macOS](https://www.mongodb.com/docs/manual/tutorial/install-mongodb-on-os-x/) 
[MongoDB Compass](https://www.mongodb.com/docs/compass/master/install/)
[MongoDB Shell](https://www.mongodb.com/docs/mongodb-shell/install/)


or


Steps:
1. Head on over to [MongoDB's website](https://www.mongodb.com/try/download/community) and scroll down to *MongoDB Community Server Download* to download it.


2. Select the current version and required platform as well as the appropriate package if non of these is selected.


3. Go to your downloads folder and extract the files by double-clicking the downloaded file.


4. Open your HyperTerminal while keeping your launchpad open. Place them side by side.


5. In your terminal type "sudo mv" followed by a space. Drag the mongoDB folder to your terminal and release. You should see a path provided after the command is entered, follow it up with a space and the location of "/usr/local/mongodb".


6. Assuming everything was typed correctly, we will be prompted for the password to our device, enter the password that you would normally use when logging on to your device and hit enter.


7. In the terminal type "open /usr/local/mongodb" and enter. This should provide the launchpad which should be highlighted in the MongoDB folder.


8. Next we will need to add it to our environment variables. we accomplish this step by typing the following command in our terminal "cd ~". This will take us to our home folder where we will then type the following "touch .bash_profile" and press enter.


9. In the terminal type "ls -a" which provides a list of files. By scrolling up, you should see the file that was just created called .bash_profile.


10. We will now need to edit that file. In the terminal, at your current location, type the following: "vim .bash_profile" and enter. Hit the letter i on your keyboard, this action to result in an --INSERT-- prompt appearing on your terminal.


11. Still on your terminal and after having clicked the i key on your keyboard, you must now type "export PATH=$PATH:/usr/local/mongodb/bin". Hit the ESC key to exit insert mode in vim. Type ":wq!" and hit the enter key to exit and save


12. We will now be creating a folder on our local device which will serve as the local data storage location for MongoDB. We will do so by typing the following command in our terminal: "sudo mkdir -p /data/db" and entering. You may be asked for your Mac password again, enter the password for your device if this is the case.


13. Next, we are required to set permissions for the data directory for the current user. Let's begin by verifying our username in the terminal, type "whoami" and pressing enter. The response is your username. Proceed by entering "sudo chown yourusername /data/db". When you hit enter it will once again request your password.


14. Force quit your terminal and open a fresh terminal instance where you will enter Mongo --version. Your response should indicate the version of the download. If this is the case, you have been successful with your setup.


Note: If you ran into issues and were not able to successfully install. Google any errors you may come across or reach out to the organization for assistance.


#### FOR Windows

***Recommended***
Follow the instructions:
[MongoDB Install on Windows](https://www.mongodb.com/docs/manual/tutorial/install-mongodb-on-windows/) 
[MongoDB Compass](https://www.mongodb.com/docs/compass/master/install/)
[MongoDB Shell](https://www.mongodb.com/docs/mongodb-shell/install/)


or 


We will begin by installing MongoDB onto our local system.


Steps:
1. Head on over to [MongoDB's website](https://www.mongodb.com/try/download/community) and scroll down to *MongoDB Community Server Download* to download it.


2. Select the current version and required platform (Windows) as well as the MSI package if not already selected. Click the download button.


3. Go to your downloads folder and find the installation wizard called MongoDB blah, blah, blah and ending with a .msi extension, this is your installer.


4. Double-click on it to launch the installation wizard.


5. Click next, accept the terms of the license, and choose the "complete" installation. Proceed by selecting "Run service as a network service user" and make note of this directory path located under the Data Directory: filed.


6. Proceed by selecting Next, uncheck install MongoDB compass and click Next. Finally, click Install to start the installation.


7. Once the installation has completed simply click Finish and you'll exit out of the installation wizard.


8. Go into your C-drive, and look at your program files you should see a folder called MongoDB with a server folder inside it.


9. The next thing we will do is set up the data folder where MongoDB will save your databases on your local system. Head on over to your C drive, and create a new folder called data. Within the data folder, create a folder called db. Within the directory path, verify that your device indicates you are on the "This PC > Local Disk (c:) > data > db"


10. Head into Explorer and go into your C-drive, Scroll down until you see Program Files, double click on that and scroll down to find MongoDB, go inside that folder and inside the folder called server. Double-click on the folder with the version number in the bin where you will see all the folders needed for MongoDB.


11. Open your terminal and change the directory to your home folder by typing "cd ~" and enter. Proceed by entering "touch .bash_profile" and hit enter to create the file. Verify the file has been created by typing the following command "ls -a". On the list that appears, search for the .bash_profile file.


12. Having just created that file, we will now be editing it. Still in the terminal, type the following: "vim .bash_profile" and enter. This has opened the file in the command line


13. While in the .bash_prifile, enter the lowercase i on your keyboard which should result in enabling the insert mode. You can confirm you are on the insert mode if you see "--INSERT--" on your terminal screen. Enter the following command:
"alias mongod="/c/Program\ files/MongoDB/Server/versionnumber/bin/mongod.exe" followed by
"alias mongo="/c/Program\ files/MongoDB/Server/versionnumber/bin/mongo.exe" where the version number is the number of the version you downloaded up to the first digit after the decimal.


Here's an example of what mine would look like:
"alias mongod="/c/Program\ files/MongoDB/Server/6.0/bin/mongod.exe"
"alias mongo="/c/Program\ files/MongoDB/Server/6.0/bin/mongo.exe"


14. To exit vim simply hit the ESC key on your keyboard followed by ":wq!" and enter.


15. We will now verify that we have successfully completed the installation. To do so we must first close down the terminal and re-open it. Type the following: "mongo --version" and enter.


Note: If you ran into issues and were not able to successfully install. Google any errors you may come across or reach out to the organization for assistance.


## Resources

[MongoDB Install on macOS](https://www.mongodb.com/docs/manual/tutorial/install-mongodb-on-os-x/)
[MongoDB Install on Windows](https://www.mongodb.com/docs/manual/tutorial/install-mongodb-on-windows/)











