# NoSQL Database with MongoDB - Setup Environment


## Table of Contents
1. Setup Environment



## Setup Environment


### Installing MongoDB for MAC

We will begin by installing MongoDB onto our local system.


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


13. Next, we are required to set permissions for the data directory for the current user. Let's begin by verifying our username in the terminal, type "whoami" and press enter. The response is your username. Proceed by entering "sudo chown yourusername /data/db". When you hit enter it will once again request your password.


14. Force quit your terminal and open a fresh terminal instance where you will enter Mongo --version. Your response should indicate the version of the download. If this is the case, you have been successful with your setup.


Note: If you ran into issues and were not able to successfully install. Google any errors you may come across or reach out to the organization for assistance.


### Installing MongoDB for Windows

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
"alias mongo="/c/Program\ files/MongoDB/Server/versionnumber/bin/mongo.exe" where the versionnumber is the number of the version you downloaded up to the first digit after the decimal.


Here's an example of what mine would look like:
"alias mongod="/c/Program\ files/MongoDB/Server/6.0/bin/mongod.exe"
"alias mongo="/c/Program\ files/MongoDB/Server/6.0/bin/mongo.exe"


14. To exit vim simply hit the ESC key on your keyboard followed by ":wq!" and enter.


15. We will now verify that we have successfully completed the installation. To do so we must first close down the terminal and re-open it. Type the following: "mongo --version" and enter.


Note: If you ran into issues and were not able to successfully install. Google any errors you may come across or reach out to the organization for assistance.

















