# Development environments on the Ubuntu droplets:

1. **Connect via Bitvise using the provided key**:

   - Instruct Jake and Jun to download and install Bitvise SSH Client on their local machines.
   - Ask them to launch the Bitvise SSH Client and click on the "New" button to create a new connection.
   - In the "Host" field, they should enter the respective IP addresses (Jake: 152.42.216.59, Jun: 128.199.235.83).
   - Under the "Username" field, they should enter "root".
   - Import the keys provided.
   - Click "Open" to establish the connection.

2. **Connect to the terminal and familiarize with console & file management**:

   - Once connected, Jake and Jun can access the terminal and explore the file system using basic Linux commands like `ls`, `cd`, `mkdir`, `touch`, etc.
   - Encourage them to practice navigating the file system and creating/modifying files and directories.

3. **Set up Python and virtual environment**:

   - Install Python and the virtual environment package using the following commands:
     ```
     sudo apt-get update
     sudo apt-get install -y python3 python3-venv
     ```
   - Create a virtual environment for the FastAPI project:
     ```
     python3 -m venv fastapi_env
     ```
   - Activate the FastAPI virtual environment:
     ```
     source fastapi_env/bin/activate
     ```

4. **Set up Node.js and Quasar**:

   - Install Node.js using the following commands:
     ```
     curl -sL https://deb.nodesource.com/setup_14.x | sudo -E bash -
     sudo apt-get install -y nodejs
     ```
   - Install the Quasar CLI globally:
     ```
     npm install -g @quasar/cli
     ```
   - Navigate to the Quasar project directory and install the dependencies:
     ```
     cd quasar_project
     npm install
     ```

5. **Set up PM2 to run Python and Node.js applications**:

   - Install PM2 using the following command:
     ```
     npm install -g pm2
     ```
   - Teach them how to use PM2 to manage their Python and Node.js processes, such as starting, stopping, and monitoring the applications. search about ecosystem.js to autorun your application

6. **Install Nginx and PHP**:

   - Install Nginx and PHP using the following commands:
     ```
     sudo apt-get install -y nginx php-fpm
     ```
   - Explain the basic Nginx configuration and how to set up PHP integration with Nginx.

7. **Install PostgreSQL**:

   - Install PostgreSQL using the following command:
     ```
     sudo apt-get install -y postgresql postgresql-contrib
     ```
   - Guide them through the process of creating a new database, user, and setting up basic PostgreSQL configurations.

8. **Deploy the FastAPI, Quasar, and PHPMaker applications**:

   - For the FastAPI application:
     - Clone the repository
     - Install dependencies in the `fastapi_env` virtual environment
     - Start the FastAPI application using PM2
   - For the Quasar application:
     - Clone the repository
     - Install dependencies using `npm install`
     - Build the Quasar application using `quasar build`
     - Start the Quasar application using PM2
   - For the PHPMaker application:
     - Clone the repository
     - Configure the necessary PHP settings and dependencies

9. **Set up subdomains and proxy**:
   - Configure Nginx to handle the routing as follows:
     - `/api` -> FastAPI application
     - `/mng` -> PHPMaker application
     - `/` -> Quasar application
