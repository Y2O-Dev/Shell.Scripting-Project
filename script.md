# Automation of Website Template Deployment on Ubuntu Server with Apache2

## Prerequisites
1. An AWS Ubuntu server with SSH access
2. Basic knowledge of Linux command line

## Step 1: Connect to the Ubuntu Server
- There are several ways to connect to a remote server. In this project, I created a *config* file within the **/.ssh** directory.
- I populated it with as follows:
> - Host: Any name of your choice (I named it *webscript*)
> - HostName: The Public IP of the instance
> - User: I used Ubuntu because its the default 
user given to  the server by AWS
> - Port: I did not add the port block because the SSH default port is 22
- On the terminal, I only need few commands to gain access to my server:

> `ssh webscript`

## Step 2: Writting The .sh File
- Using the vi editor:
> - Open a new file with a choice name and .sh extension. In my case, I gave it *webscript.sh* and open it with:

> `vi webscript.sh`

> - Input the code
> - There should be comment explaining what the code does
> - Press the `Esc` key on the keyboard, followed by `CTRL ZZ` to save and exit the editor

## Step 3: Make the Script Executable
- Make the script executable using the below command:

> `chmod +x webscript.sh`

## Step 4: Run the Script
- To run the script witout given an absolute path, the current directory can be added to the $PATH environmental variable with this command:

> `PATH=$PATH: .`

- The script file can then be called using a relative path
- Although this is considered a security risk
## Step 4: Run the Script

### The script will perform the following steps:

### Installing Dependencies
- Updates the package lists.
- Installs wget, unzip, and apache2 packages.

### Start & Enable Services
- Starts the Apache2 service.
- Enables the Apache2 service to start on boot.

### Creating a Temp Directory

- Creates a temporary directory /tmp/webfiles to hold the downloaded website template.

### Download and Extract the Template
- Downloads the website template ZIP file using wget.
- Extracts the contents of the ZIP file using unzip.
- Copies the extracted template files to the Apache2 web root directory /var/www/html/.

### Restart Apache2 Service
- Restarts the Apache2 service to apply the changes made during the deployment.
- This will print the status of the service after completion and also list the contents of 
the /var/www/html/

![status](https://github.com/Y2O-Dev/Shell.Scripting-Project/assets/114786664/d9c2b51b-524c-4b58-85a7-2959c6090830)

![ls-l](https://github.com/Y2O-Dev/Shell.Scripting-Project/assets/114786664/f1e25d74-6ab7-459d-8a62-dbcc43575f2d)

### Clean Up
- Removes the temporary files used during the deployment.

- The contents of the website displayed after modifying the securita group to listen on port 80

![webpage1](https://github.com/Y2O-Dev/Shell.Scripting-Project/assets/114786664/54c6740d-1ee2-4380-bbb2-08010f5b2463)

![webpage2](https://github.com/Y2O-Dev/Shell.Scripting-Project/assets/114786664/03e491c6-839e-42db-9453-56916612d703)

![webpage3](https://github.com/Y2O-Dev/Shell.Scripting-Project/assets/114786664/b7c4440e-884b-4764-8766-18eb896e9824)

---
### END