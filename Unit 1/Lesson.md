# Module 1: Introduction to MongoDB


## Table of Contents
1. Installation and setup


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

To install MongoDB and its tools on Windows, you can follow these steps:

1. Visit the MongoDB download page at https://www.mongodb.com/try/download/community and select the Windows version you prefer.

2. Download the MongoDB Community Edition installer appropriate for your Windows version (e.g., MSI for Windows 64-bit).

3. Once the download is complete, open the installer package (.msi file) and follow the installation wizard.

4. In the installation wizard, choose the "Complete" setup type to install both the MongoDB server and the MongoDB tools.

5. Specify the installation directory where MongoDB will be installed. By default, it is installed in `C:\Program Files\MongoDB\Server\<version>`.

6. Configure the MongoDB server as a Windows service by selecting the "Run the service as Network Service user" option. This allows the MongoDB service to start automatically when Windows starts.

7. Click the "Install" button to start the installation process.

8. Once the installation is complete, MongoDB is ready to use. You can access MongoDB from the command line by opening a new Command Prompt window and running the `mongo` command.

9. Additionally, you can use MongoDB Compass, a graphical user interface tool, to interact with MongoDB. You can download MongoDB Compass from the MongoDB download page and install it on your Windows system.

That's it! MongoDB and its tools are now installed on your Windows machine. You can start using MongoDB by running the `mongo` command in the Command Prompt or by launching MongoDB Compass. Remember to refer to the MongoDB documentation for further instructions on how to use MongoDB and its various tools effectively.

